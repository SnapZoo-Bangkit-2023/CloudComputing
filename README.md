# SnapZoo, Indonesian Zoo App

## Team C23-PS157 Contributors
* Angger Muhammad Rizqi (M286DKX3783) - [GitHub@Anggerm](https://github.com/Anggerm) - Machine Learning - Universitas Negeri Semarang
* Bahtiar Hasan (C172DSX3347) - [GitHub@bhtiar](https://github.com/bhtiar) - Cloud Computing - Universitas Gunadarma
* Dyah Nabila Yulianto (M286DSY0323) - [GitHub@dyahnabila-y](https://github.com/dyahnabila-y) - Machine Learning - Universitas Negeri Semarang
* Hafidzurrohman Saifullah (C172DKX4931) - [GitHub@Hafidzurr](https://github.com/Hafidzurr) - Cloud Computing - Universitas Gunadarma
* Muhammad Prasetyo Nugroho (M282DSX1345) - [GitHub@MuhammadPrasetyoN](https://github.com/MuhammadPrasetyoN) - Machine Learning - Universitas Negeri Malang
* Natasya Wulandari (A172DSY4927) - [GitHub@natasyaawldr](https://github.com/natasyaawldr) - Mobile Development - Universitas Gunadarma

## About
The Snapzoo application is an application based on animal identification through photo activities, which can help zoo visitors learn about wild animals in a more interactive and fun way. Using image recognition technology, users can photograph animals encountered in zoos and the application will identify the type of animal and provide detailed information about the habitat, behavior and unique characteristics of the animal.

## Presentation and Demo Video
```
https://youtu.be/
```

## Android APK File (Minimum Android SDK 21)
Link: https://drive.google.com/drive/folders/1fnTmL0c1Yma-tWOXsn2Nt3QHWrhdPydq?usp=sharing<br/>
Alternative Link: 

## Wireframe && Mock-Up
```
https://www.figma.com/file/nU6gWLv3l2B0C3MaX4FFeV/SnapZoo?type=design&node-id=0-1
```

## REST API Documentation
```
https://documenter.getpostman.com/
```

## SnapZoo Content References
The description in snapzoo, our team prefer to observation data in internet. For details, please refer to this link.
```
https://docs.google.com/spreadsheets/
```

## App Features
![Feature 1](https://github.com/SnapZoo-Bangkit-2023/SnapZoo-Documentation/blob/6c5375c83977d400b28fd00b01914052e3e641fa/asset/feature_1.png)
![Feature 2](https://github.com/SnapZoo-Bangkit-2023/SnapZoo-Documentation/blob/6c5375c83977d400b28fd00b01914052e3e641fa/asset/feature_2.png)
![Feature 3](https://github.com/SnapZoo-Bangkit-2023/SnapZoo-Documentation/blob/d24cf9c931d94080aae89720ac62d2106c051f22/asset/feature_3.png)
![Feature 4](https://github.com/SnapZoo-Bangkit-2023/SnapZoo-Documentation/blob/d24cf9c931d94080aae89720ac62d2106c051f22/asset/feature_4.png)

* The SnapZoo application is specifically designed for users who want to identify and learn about animals they encounter in the zoo.
* Upload image from camera to predict its animal you wanna know.
* Search various Animal in Zoo by typing on search bar.
* Information about Animal inclunding name, classification, images, and other related about animal.

## Technology
* Android Studio IDE to develop the Android application.
* Google Cloud Platform as deployment platform for REST API and ML model.
* Tensorflow and Keras to develop, train, and deploy ML model.

## Integration Method
SnapZoo consists of three components, Android, Cloud Computing, and Machine Learning. Basically, to integrate these, Cloud Computing acts as service to bridge communication between Android and Machine Learning. Here is a simple illustration on how our integration method works.
![Integration Method](https://github.com/SnapZoo-Bangkit-2023/SnapZoo-Documentation/blob/39e255479826d93f08ade5b1df1e31364df763cf/asset/integration.png)
Integration method explanation:
1. The Android app allows users to capture a picture of an animal they encounter.
2. The App Engine, which serves as a service, handles the requests from the app.
3. Depending on the request, the App Engine services access the REST API. If the request is for animal description information, it queries the pre-existing JSON data in the App Engine. If the request is for animal image prediction, the image is sent to the ML model.
4. Once the REST API has finished processing, the App Engine services return the results as JSON literals to the Android app. This includes the prediction result and the animal description.
5. The Android app processes the received JSON literals and displays the relevant information to the user.

## Estimate Google Cloud Platform Pricing
![GCP Pricing](https://github.com/SnapZoo-Bangkit-2023/SnapZoo-Documentation)

## Android Studio Project Installation
### Components
Wacayang Android app is developed using Android Studio IDE. Here are components that we used.
* Developed using [Kotlin](https://kotlinlang.org/) language.
* Composed by [Activity](https://developer.android.com/reference/android/app/Activity) and [Fragment](https://developer.android.com/guide/fragments).
* Using [RecycleView](https://developer.android.com/guide/topics/ui/layout/recyclerview) and its adapater for item listing.
* [CameraX](https://developer.android.com/training/camerax) to utilize mobile camera features including flash, front/back camera, and more.
* Using [Retrofit](https://square.github.io/retrofit/) library for network request.
* Using [ExoPlayer](https://exoplayer.dev/) to play videos.
* [BottomNavigation](https://developer.android.com/reference/com/google/android/material/bottomnavigation/BottomNavigationView) to navigate between main menus (Home, Favorite, and Settings).
* Connected to [Firebase Auth](https://firebase.google.com/docs/auth) for Google and anonymous sign in.
* Utilize [LiveData](https://developer.android.com/topic/libraries/architecture/livedata), [ViewModel](https://developer.android.com/topic/libraries/architecture/viewmodel), and [Repository](https://developer.android.com/codelabs/basic-android-kotlin-training-repository-pattern) pattern for Single Source of Truth (SSOT)

### Requirements
* Android Studio Bumblebee 2021.1.1 Patch 2
* Minimum Android SDK 21

### Workflow
#### 1. Clone The Project and Open It in Android Studio
```
git clone https://github.com/Wacayang-Bangkit-2022/Wacayang-MobileDev.git
```
#### 2. Connect the Project to Your Firebase Auth
* Head to your [Firebase Console](https://console.firebase.google.com/).
* Then create or use your existing Firebase project.
* Activate Firebase Authentication feature.
* Open `Project Settings -> General`, select `New App`, and choose Android app.
* Fill debug SHA1 fingerprint. You can find this by execute `Gradle -> signingReport` on Android Studio.
* After the new Firebase app added, you will see your debug SHA1 added to that Firebase app. You can add another SHA1 such as your signed app SHA1. You can find your signed app SHA1 by executing this command on terminal. But, you will need to create your [Keystore](https://developer.android.com/studio/publish/app-signing#generate-key) first
```
keytool -list -v -keystore <your keystore path> -alias <your alias>
```
* Install [Firebase SDK](https://developer.android.com/studio/write/firebase) to your Android Studio project.
* Download the `google-service.json` from your Firebase Console, and copy it to the `app` folder of your Android Studio project.
#### 3. Run or Build The App
After you open the project, wait for the Gradle to finish building first. Then you can choose to build debug app by using `Run -> Run'app'`. Or you can build signed App by head to `Build -> Generate Signed Bundle/APK`.

## Cloud Computing Project Installation
### Components and Requirements
* Firebase Project and Firebase Storage For Put The Folder Animal Photo.
* REST API developed using Flask.
* Deployed REST API running as service on Google App Engine with Model ML(h5) and JSON Description.
### Workflow
#### 1. Clone The Project and Open It in Your Favorite IDE And Make a Firebase Project
```
https://firebase.google.com/
```
```
git clone https://github.com/
```
* Make a folder "foto" in firebase storage and put all foto in that's folder.
* Change The URL Link Animal Image You Already Take it From Firebase Storage or foto folder in Description.json (make sure you open first the image in browser and take the long url).
#### 2. Try to Running The RestAPI in Local
* Open The folder RestAPI You Already Clone in Your Visual Studio Code. 
* Open New Terminal `Install Flask"pip install flask" -> Run the main.py -> "python main.py"` (make sure other library like pillow, and kerastenserflow already install in your local).
* Choose `Generate New Private Key`, and your private key JSON file will be downloaded.
* Open Postman and test the URLBASE `For Predict put /predict in last URLBASE "Use Post -> key"file"-> and put animal image` and `For Description put /deskripsi in last URLBASE "Use Get -> Send`
#### 3. Deploy REST API to Cloud Run
* There will be two service running on Cloud Run.
* First, go to `wacayang_general_api` folder via terminal. And run `gcloud run deploy` command. Fill the rest of required fields. When it finish, it should shows your deployed service URL.
* Do the same for `wacayang_ai_api` folder, run `gcloud run deploy` command. Fill the rest of required fields. When it finish, it should shows your deployed service URL.
* These URL will be used by Android app to send network request. Replace the URL on `ApiService.kt` inside your Android Studio project to make it works with your deployed API.
* Go to your Cloud Console then head to your Cloud Run tab.
* Open your deployed `wacayang_general_api` service and create new revision by choosing `Edit & Deploy New Revision`.
* On Variable and Secrets tab, add new variable for `DB_NAME`, `DB_USER`, `DB_PASS`, and `INSTANCE_CONNECTION_NAME`. This necessary so your service can connect to your database. Fill these information based on your SQL database instance, then choose `Deploy` to create new revision.
#### Our Deployed REST API URL
Please head to this link for our detailed REST API documentation.
```
https://documenter.getpostman.com/view/20994859/UyxqDPV6
```

## Machine Learning Project Installation
### Components
* Image Pre-processing
* Image Augmentation
* Early Stopping
* Callbacks
* Model Checkpoint
* Convolutional Neural Network (CNN)
* Transfer Learning
  * DenseNet121
  * InceptionV3
  * ResNet152V2
* Model Evaluate
* Accuracy and Loss Graph
### Requirements
* [Google Colaboratory](https://colab.research.google.com/) or [Jupyter Notebook](https://jupyter.org/install).
* Kaggle API Token.
* Latest Tensorflow Version 2.8.2.
* Python Version 3.6 or above.

### Dataset
* [Animal Image Dataset](https://bit.ly/animalimagedatasets)
<p align="center"> <img src="https://github.com/SnapZoo-Bangkit-2023/SnapZoo-Documentation"></p>
<p align="center">Dataset Preview</p>
<p align="center">(Left to right) Gajah, Harimau, Monyet, Rusa, and Ular</p>

### Workflow
<!-- 1. [Generate Kaggle API token](https://github.com/Kaggle/kaggle-api#api-credentials) to get `kaggle.json` file
2. Open the `.ipynb` file in Google Colab or Jupyter Notebook:
   * [Baseline Model (CNN)](https://colab.research.google.com/github/Wacayang-Bangkit-2022/Wacayang-MachineLearning/blob/main/Wayang%20Classifier/Base%20Model%20(Simple%20CNN)/Baseline_Model.ipynb)
   * [DenseNet121](https://colab.research.google.com/github/Wacayang-Bangkit-2022/Wacayang-MachineLearning/blob/main/Wayang%20Classifier/Model%20with%20DenseNet121/Wacayang_DenseNet_Model.ipynb)
   * [InceptionV3](https://colab.research.google.com/github/Wacayang-Bangkit-2022/Wacayang-MachineLearning/blob/main/Wayang%20Classifier/Model%20with%20InceptionV3/Wacayang_InceptionV3_Model.ipynb)
   * [ResNet152V2](https://colab.research.google.com/github/Wacayang-Bangkit-2022/Wacayang-MachineLearning/blob/main/Wayang%20Classifier/Model%20with%20ResNet152V2/Wacayang_ResNet_Model.ipynb)
3. Click `Copy to Drive`  or Click `File` > `Save a copy in Drive`. This will allow you to run and edit the `.ipynb` file in your own Google Drive account
4. Upload your `kaggle.json` file (API Token)
5. Run every cell in the `.ipynb` file
6. Download the model `.h5` file by left clicking the `.h5`file in the Colab directory (Automatically saved to `/content/` file by Model Checkpoint) -->
