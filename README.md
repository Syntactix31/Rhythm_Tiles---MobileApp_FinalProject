# Rhythm Tiles
Rhythm Tiles is a mobile application game designed to be a fun ear-training and muscle memory exercise with popular music variety for users.  
The tech stack utilizes a React Native Framework with JSX elements to create a structured and presentable application that lays the foundation for improved functionality and feature additions.
This application was emulated, tested, and debugged using Android Studio IDE and is the suggested method for system building with its Gradle compiler and native android application development capabilties.




## Accreditation
Levi Moreau - UI/UX, Interactivity and Metrics
Jiro Roales - Game Mechanics
Theo Sanchez - Persistent Data Storage 






/**\*** ENVIRONMENT INSTALLATION PROCEDURES **\***\

## npm req

npm install @react-navigation/native @react-navigation/native-stack

npm install react-native-gesture-handler react-native-safe-area-context react-native-screens

npm install react-native-linear-gradient

npm install react-native-sound

npm install react-native-async-storage/async-storage

## npm

npm start -- --reset-cache

## CLI

npx react-native start --reset-cache

// For better termination of audio state insert this into android MainApplication java file (keep this as a reference)

override fun onCreate() {
super.onCreate()

    reactHost.reactInstanceManager?.addReactInstanceEventListener(object : ReactInstanceManager.ReactInstanceEventListener {
      override fun onHostResume() {}
      override fun onHostPause() {}
      override fun onHostDestroy() {
        try {
          val audioManager = getSystemService(Context.AUDIO_SERVICE) as AudioManager
          audioManager.mode = AudioManager.MODE_NORMAL
        } catch (e: Exception) {
          android.media.AudioManager::class.java.getMethod("stopAllSounds").invoke(null)
        }
      }
    })



    loadReactNative(this)

}
