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
This app use Animal images provided by Wikimedia on Public Domain Licences. For details, please refer to this link.
```
https://docs.google.com/spreadsheets/
```

## App Features
![Feature 1](https://github.com/SnapZoo-Bangkit-2023/SnapZoo-Documentation/blob/6c5375c83977d400b28fd00b01914052e3e641fa/asset/feature_1.png)
![Feature 2](https://github.com/SnapZoo-Bangkit-2023/SnapZoo-Documentation/blob/6c5375c83977d400b28fd00b01914052e3e641fa/asset/feature_2.png)
![Feature 3]()
![Feature 4](https://github.com/SnapZoo-Bangkit-2023/SnapZoo-Documentation)
* Search various Animal in Zoo by typing on search bar.
* Upload image from camera to predict its animal you wanna know.
* Information about Animal inclunding name, classification, images, and other related about animal.

## Technology
* Android Studio IDE to develop the Android application.
* Google Cloud Platform as deployment platform for REST API, database, and ML model.
* Tensorflow and Keras to develop, train, and deploy ML model.

## Integration Method
Wacayang consists of three components, Android, Cloud Computing, and Machine Learning. Basically, to integrate these, Cloud Computing acts as service to bridge communication between Android and Machine Learning. Here is a simple illustration on how our integration method works.
![Integration Method](https://github.com/SnapZoo-Bangkit-2023/SnapZoo-Documentation)
Integration method explanation:
1. Android app send a network request using Retrofit library. This request has JWT token as Authorization header.
2. Cloud Run acts as service to serve request from the app. It will verify the token first before proceed.
3. After token is verified, Cloud Run services will access back-end app depending on the request. If it looking for user or wayang information, it will query to SQL database. If it looking for wayang image prediction, then it will post that image to ML model.
4. After back-end app finished processing, Cloud Run services will return the result as JSON literals to the Android app.
5. Android app will process the JSON literals and show relevant information to the user.

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
* SQL database running on Google Cloud Platform
* REST API developed using Node.JS, Express, and Flask.
* Deployed REST API running as service on Google Cloud Run.
### Workflow
#### 1. Clone The Project and Open It in Your Favorite IDE
```
git clone https://github.com/Wacayang-Bangkit-2022/Wacayang_CloudComputing.git
```
#### 2. Get Service Account Key from Firebase
* Open your last Firebase project used for Android Studio project installation
* Go to `Project Settings -> Service Accounts`
* Choose `Generate New Private Key`, and your private key JSON file will be downloaded.
* Rename your private key as `serviceAccountKey.json`
* Copy that file to your cloned project, both inside `wacayang_general_api` and `wacayang_ai_api` folder.
#### 3. Create SQL Instance on GCP
* Open your Cloud Console, head to `SQL -> MySQL -> Create New Instance`
* Create new database on your newly created SQL instance.
* Create necessary tables as showed on this schema below.
![Database Schema](https://github.com/SnapZoo-Bangkit-2023/SnapZoo-Documentation)
* Setup your database connection such as `DB_USER`, `DB_PASS` on the `Connection` tab.
#### 4. Deploy REST API to Cloud Run
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
