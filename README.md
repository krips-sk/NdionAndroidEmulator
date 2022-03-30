# NdionAndroidEmulator

example Path to import Emulator files:
C:\Users\WDSI\AndroidStudioProjects\Ndion\app\build.gradle

###########################Tried to add Linear gradient####################################
( https://www.npmjs.com/package/react-native-linear-gradient#android )

Run npm install react-native-linear-gradient --save
Then:

in android/settings.gradle
...
include ':react-native-linear-gradient'
project(':react-native-linear-gradient').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-linear-gradient/android')
in android/app/build.gradle add:
dependencies {
    ...
    implementation project(':react-native-linear-gradient')
}
and finally, in android/app/src/main/java/com/{YOUR_APP_NAME}/MainActivity.java for react-native < 0.29, or android/app/src/main/java/com/{YOUR_APP_NAME}/MainApplication.java for react-native >= 0.29 add:
//... 
import com.BV.LinearGradient.LinearGradientPackage; // <--- This! 
//... 
@Override
protected List<ReactPackage> getPackages() {
  return Arrays.<ReactPackage>asList(
    new MainReactPackage(),
    new LinearGradientPackage() // <---- and This! 
  );
}
Windows (WPF)
in windows/MyApp.sln Add -> Existing Project: node_modules/react-native-linear-gradient/windows/LinearGradientWPF/LinearGradientWPF.csproj

in windows/MyApp/MyAppWPF/MyAppWPF.csproj Add -> Reference -> LinearGradientWPF

in windows/MyApp/MyAppWPF/AppReactPage.cs add: using LinearGradient; and

public override List<IReactPackage> Packages => new List<IReactPackage>
{
  ...
  new LinearGradientPackage()
}
