Run script
Run scripts 5 and 6 with the brand name as param in lowercase (for staging)
Optimize, convert to web and update assets
Run launcher icons
Run native splash screen 
Create configurations in Xcode for debug, release, and profile
Create production-pinaflare and staging-pinaflare schemes in ios/Runner.xcodeproj/xcshareddata/xcschemes
Select Runner in TARGETS and:
- Update Packaging in Build Settings inside Xcode`
- Update Packaging inside Build Settings of OneSignal extension
- Create brand specific code signing entitlements in ios/Runner/*.entitlements
- Update Signing in Build Settings inside XCode
Add tertiary color into white_label.yaml
Update Facebook client token, app id, and display name in Info.plist
Update Facebook app id and client token in android strings.xml
Update google geo api key meta tag in AndroidManifest.xml
Create Firebase apps:
- Create android app in firebase
- Create iOS app in firebase
- Create web app in Firebase
Run `flutterfire configure --project=pina-flare -i com.pinaflare.app` to update the firebase_options.dart file
Download google-services.json from Firebase
- Place the json file into android/app
Download GoogleService-Info.plist from Firebase
- Place the plist file into ios/config/pinaflare/production and ios/config/pinaflare/staging
Update ios/firebase_app_id_file.json file
Update bundle id in side `target.build_configurations.each` loop in Podfile file
Update all env variables in .env
Update app description in web/manifest.json
Update keys in web/index.html
Update app version and description in pubspec.yaml
Update assets in web/splash
Create a new signing key with command `keytool -genkey -v -keystore pinaflare.keystore -storepass <storePassword> -alias <alias> -keypass <keyPassword> -keyalg RSA -keysize 2048 -validity 10000`
Create a new file from android/app/key.properties template with the passwords and alias
Update build.gradle to use your new file instead of key.properties
Update .firebaserc with you firebase project name
Update the site names in firebase.json
Update brand name and email in TOS static pages inside web folder
Add all brand domains into Redirect Urls in Supabase for staging and production

Add pinaflare domain into Resend

Update BRAND_ID and ENVIRONMENT in copy-google-plist.sh script in ios folder

Add email templates to emails media in Supabase in `brand/template/en.html` and `brand/template/th.html`

Update the Apple Client IDs with the brand bundle id

Add AUTH_EXTERNAL_APPLE_SECRET to secrets with the Apple Secret Key (for OAuth)
