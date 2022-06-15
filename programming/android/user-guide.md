---
layout: default-layout
title: Dynamsoft Document Normalizer for Android - User Guide
description: This is the user guide of Dynamsoft Document Normalizer for Android SDK.
keywords: user guide, android
needAutoGenerateSidebar: true
needGenerateH4Content: true
noTitleIndex: true
---

# Getting Started with Android

## Requirements

- Operating systems:
  - Supported OS: Android 5 or higher (Android 7 or higher recommended).
  - Supported ABI: armeabi-v7a, arm64-v8a, x86 and x86_64.

- Environment: Android Studio 3.4+.

## Build Your First Application

In this section, let's see how to create a HelloWorld app for normalizing documents from camera video input.

>Note:
>
>- Android Studio 4.2 is used here in this guide.
>- You can [get the source code of the HelloWord app here](https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/android/HelloWorld).

### Create a New Project

1. Open Android Studio, select **File > New > New Project**.

2. Choose the correct template for your project. In this sample, we use **Empty Activity**.

3. When prompted, choose your app name 'HelloWorld' and set the **Save** location, **Language**, and **Minimum SDK** (we use 21 here).
    > Note:
    >
    > - With **minSdkVersion** set to 21, your app is compatible with more than 94.1% of devices on the Google Play Store (last update: March 2021).

### Add the SDK

There are two ways to add the SDK into your project - **Manually** and **Maven**.

#### Add the Library Manually

1. Download the SDK package from the <a href="https://www.dynamsoft.com/document-normalizer/downloads/?utm_source=docs" target="_blank">Dynamsoft website</a>. After unzipping, You can find the following **aar** files under the **DynamsoftDocumentNormalizer\Lib** directory:

   | File | Description |
   |---------|-------------|
   | `DynamsoftDocumentNormalizer.aar` | The Dynamsoft Document Normalizer SDK, including document normalizer related APIs. |
   | `DynamsoftCore.aar` | The core library of Dynamsoft's capture vision SDKs, including common basic structure and license related APIs. |
   | `DynamsoftIntermediateResult.aar` | The common intermediate result library of Dynamsoft's capture vision SDKs, including all intermediate results produced in the process of decoding a barcode, recognizing a label or normalizing a document. |
   | `DynamsoftImageProcessing.aar` | The image processing library of Dynamsoft's capture vision SDKs, including image processing algorithms and APIs. |
   | `DynamsoftCameraEnhancer.aar` | The Dynamsoft Camera Enhancer SDK, including camera control and frame preprocessing APIs.  |

2. Copy the above five **aar** files to the target directory `HelloWorld\app\libs`

3. Open the file `HelloWorld\app\build.gradle` and add reference in the dependencies:

    ```groovy
    dependencies {
         implementation fileTree(dir: 'libs', include: ['*.aar'])

         def camerax_version = '1.1.0-rc01'
         implementation "androidx.camera:camera-core:$camerax_version"
         implementation "androidx.camera:camera-camera2:$camerax_version"
         implementation "androidx.camera:camera-lifecycle:$camerax_version"
         implementation "androidx.camera:camera-view:$camerax_version"
    }
    ```

    > Note:
    >
    > DCE 3.x is based on Android CameraX, so you need to add the CameraX dependency manually.

4. Click **Sync Now**. After the synchronization completes, the SDK is added to the project.

#### Add the Library via Maven

1. Open the file `HelloWorld\app\build.gradle` and add the remote repository:

    ```groovy
    repositories {
         maven {
            url "https://download2.dynamsoft.com/maven/aar"
         }
    }
    ```

2. Add reference in the dependencies:

   ```groovy
   dependencies {
      implementation 'com.dynamsoft:dynamsoftdocumentnormalizer:1.0.0@aar'
      implementation 'com.dynamsoft:dynamsoftcameraenhancer:3.0.0@aar'
   }
   ```

3. Click **Sync Now**. After the synchronization completes, the SDK is added to the project.

### MainActivity for Realtime Detection of Quads

#### Initialize License

1. Import the `LicenseManager` class and initialize the license in the file `MainActivity.java`.

   ```java
   import com.dynamsoft.core.LicenseManager;
   import com.dynamsoft.core.LicenseVerificationListener;
   
   public class MainActivity extends AppCompatActivity {

      @Override
      protected void onCreate(Bundle savedInstanceState) { 
         super.onCreate(savedInstanceState);
         setContentView(R.layout.activity_main);

         LicenseManager.initLicense("DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9", MainActivity.this, new LicenseVerificationListener() {
            @Override
            public void licenseVerificationCallback(boolean isSuccess, CoreException error) {
               if(!isSuccess){
                  error.printStackTrace();
               }
            }
         });
      }
   }
   ```

   >Note:  
   >  
   >- Network connection is required for the license to work.
   >- The license string here will grant you a time-limited trial license.
   >- If the license has expired, you can go to the <a href="https://www.dynamsoft.com/customer/license/trialLicense?utm_source=docs" target="_blank">customer portal</a> to request for an extension.

#### Initialize Camera Module

1. In the Project window, open **app > res > layout > `activity_main.xml`** and create a DCE camera view section under the root node.

    ```xml
    <com.dynamsoft.dce.DCECameraView
        android:id="@+id/camera_view"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent">
    </com.dynamsoft.dce.DCECameraView>
    ```

2. Import the dynamsoft camera module, initialize the camera view and bind to the created Camera Enhancer instance in the file `MainActivity.java`.

   ```java
   ...
   
   import com.dynamsoft.dce.DCECameraView;
   import com.dynamsoft.dce.CameraEnhancer;
   import com.dynamsoft.dce.CameraEnhancerException;

   public class MainActivity extends AppCompatActivity {
      private CameraEnhancer mCameraEnhancer;

      @Override
      protected void onCreate(Bundle savedInstanceState) { 

         ...

         DCECameraView cameraView = findViewById(R.id.camera_view);

         mCameraEnhancer = new CameraEnhancer(MainActivity.this);
         mCameraEnhancer.setCameraView(cameraView);
      }
   }
   ```

#### Initialize Document Normalizer

1. Import and initialize the document normalizer, bind to the created Camera Enhancer instance.

   ```java
   ...

   import com.dynamsoft.ddn.DocumentNormalizer;
   import com.dynamsoft.ddn.DocumentNormalizerException;

   public class MainActivity extends AppCompatActivity {
      
      ...

      public static DocumentNormalizer mNormalizer;

      @Override
      protected void onCreate(Bundle savedInstanceState) { 
         
         ...

         try {
            mNormalizer = new DocumentNormalizer();
         } catch (DocumentNormalizerException e) {
            e.printStackTrace();
         }

         mNormalizer.setCameraEnhancer(mCameraEnhancer);
      }
   }
   ```

2. Create a detect result listener and register with the document normalizer instance to get detected quad results.

   ```java
   ...

   import com.dynamsoft.core.ImageData;
   import com.dynamsoft.ddn.DetectedQuadResult;
   import com.dynamsoft.ddn.DetectResultListener;

   public class MainActivity extends AppCompatActivity {
      
      ...

      public static ImageData mImageData;
      public static DetectedQuadResult[] mQuadResults;
      private boolean startEditing;

      @Override
      protected void onCreate(Bundle savedInstanceState) { 
         
         ...
         
         mNormalizer.setDetectResultListener(new DetectResultListener() {
            @Override
            public void detectResultCallback(int id, ImageData imageData, DetectedQuadResult[] results) {
                if (results != null && results.length > 0 && startEditing) {
                    startEditing = false;

                    mImageData = imageData;
                    mQuadResults = results;

                    Intent intent = new Intent(MainActivity.this, QuadEditActivity.class);
                    startActivity(intent);
                }
            }
        });
      }
   }
   ```

3. Override the `MainActivity.onResume` and `MainActivity.onPause` functions to start/stop video quad detecting. After detecting starts, the Document Normalizer will automatically invoke the `detectQuad` API to process the video frames from the Camera Enhancer, then send the detected quad results to the detected result callback.

   ```java
   public class MainActivity extends AppCompatActivity {
      
      ...

      @Override
      protected void onResume() {
         mNormalizer.startDetecting();
         try {
            mCameraEnhancer.open();
         } catch (CameraEnhancerException e) {
            e.printStackTrace();
         }
         super.onResume();
      }


      @Override
      protected void onPause() {
         mNormalizer.stopDetecting();
         try {
            mCameraEnhancer.close();
         } catch (CameraEnhancerException e) {
            e.printStackTrace();
         }
         super.onPause();
      }
   }
   ```

#### Additional Steps in `MainActivity`

1. In the Project window, open **app > res > layout > `activity_main.xml`**, create a button under the root node to capture the quads detected on the image.

   ```xml
   ...

   <Button
      android:id="@+id/btn_capture"
      android:layout_width="130dp"
      android:layout_height="50dp"
      android:layout_marginBottom="8dp"
      android:onClick="onCaptureBtnClick"
      android:text="Capture"
      app:layout_constraintBottom_toBottomOf="parent"
      app:layout_constraintEnd_toEndOf="parent"
      app:layout_constraintHorizontal_bias="0.5"
      app:layout_constraintStart_toStartOf="parent" />
   ```

2. Set the flag to start quad edit activity. If the flag is set to true, the activity will be launched in the `detectResultCallback` function.

   ```java
   public class MainActivity extends AppCompatActivity {
      
      ...

      private boolean startEditing;

      ...

      public void onCaptureBtnClick(View v) {
         startEditing = true;
      }
   }
   ```

### QuadEditActivity for Interactive Editing of Quads

#### Initialize the Image Editor View

1. Create a new empty activity named `QuadEditActivity`.

2. In the Project window, open **app > res > layout > `activity_quad_edit.xml`** and create a DCE image editor view section under the root node.

    ```xml
    <com.dynamsoft.dce.DCEImageEditorView
        android:id="@+id/editor_view"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent">
    </com.dynamsoft.dce.DCEImageEditorView>

    ```

3. Import and initialize the dynamsoft image editor view in the file `QuadEditActivity.java`.

   ```java
   import java.util.ArrayList;
   import com.dynamsoft.dce.DCEDrawingLayer;
   import com.dynamsoft.dce.DCEImageEditorView;
   import com.dynamsoft.dce.DrawingItem;
   import com.dynamsoft.dce.QuadDrawingItem;
   import com.dynamsoft.ddn.DetectedQuadResult;

   public class QuadEditActivity extends AppCompatActivity {
      DCEImageEditorView mImageEditView;

      @Override
      protected void onCreate(@Nullable Bundle savedInstanceState) {
         super.onCreate(savedInstanceState);
         setContentView(R.layout.activity_quad_edit);

         mImageEditView = findViewById(R.id.editor_view);

         mImageEditView.setOriginalImage(MainActivity.mImageData);
         DCEDrawingLayer layer = mImageEditView.getDrawingLayer(DCEDrawingLayer.DDN_LAYER_ID);

         ArrayList<DrawingItem> items = new ArrayList<DrawingItem>();
         for (DetectedQuadResult r : MainActivity.mQuadResults) {
               items.add(new QuadDrawingItem(r.location));
         }
         layer.setDrawingItems(items);
      }
   }
   ```

4. Now you are free to edit your selected quad on the UI.

#### Normalize With the Selected Quad

1. In the Project window, open **app > res > layout > `activity_quad_edit.xml`**, create a button under the root node to normalize the image with the selected quad.

   ```xml
   ...

    <Button
        android:id="@+id/btn_normalize"
        android:layout_width="130dp"
        android:layout_height="50dp"
        android:layout_marginBottom="8dp"
        android:onClick="onNormalizeBtnClick"
        android:text="Normalize"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.5"
        app:layout_constraintStart_toStartOf="parent" />
   ```

2. When the `Normalize` button is clicked, the image will be normalized with the selected quad and the result activity will be launched.

   ```java
   ...

   import com.dynamsoft.ddn.DocumentNormalizerException;
   import com.dynamsoft.ddn.NormalizedImageResult;

   public class QuadEditActivity extends AppCompatActivity {

      ...

      public void onNormalizeBtnClick(View v) {
         try {
               DrawingItem item = mImageEditView.getSelectedDrawingItem();
               if(item == null)
                  item = mImageEditView.getDrawingLayer(DCEDrawingLayer.DDN_LAYER_ID).getDrawingItems().get(0);

               if(item instanceof QuadDrawingItem) {
                  mNormalizedImageResult = MainActivity.mNormalizer.normalize(MainActivity.mImageData, ((QuadDrawingItem) item).getQuad());

                  Intent intent = new Intent(QuadEditActivity.this, ResultActivity.class);
                  startActivity(intent);
               }
         } catch (DocumentNormalizerException e) {
               e.printStackTrace();
         }
      }
   }
   ```

### ResultActivity for Displaying the Normalized Image

#### Diplay the Normalized Image

1. Create a new empty activity named `ResultActivity`.

2. In the Project window, open **app > res > layout > `activity_result.xml`**, create a image view under the root node to display the result image.

   ```xml
   <ImageView
      android:id="@+id/iv_normalize"
      android:layout_width="match_parent"
      android:layout_height="match_parent"/>
   ```

3. Display the normalized image.

   ```java
   import com.dynamsoft.core.CoreException;

   public class ResultActivity extends AppCompatActivity {

      @Override
      protected void onCreate(@Nullable Bundle savedInstanceState) {
         super.onCreate(savedInstanceState);
         setContentView(R.layout.activity_result);

         ImageView ivNormalize = findViewById(R.id.iv_normalize);

         try {
               ivNormalize.setImageBitmap(QuadEditActivity.mNormalizedImageResult.image.toBitmap());
         } catch (CoreException e) {
               e.printStackTrace();
         }
      }
   }
   ```

### Build and Run the Project

1. Select the device that you want to run your app on from the target device drop-down menu in the toolbar.

2. Click the **Run app** button, then Android Studio installs your app on your connected device and starts it.

You can download the complete source code here:
- <a href="https://github.com/Dynamsoft/document-normalizer-mobile-samples/tree/main/android/HelloWorld" target="_blank">Android source code</a>
