npm install -g expo-cli eas-cli
cd freefire-tournament
npm install
expo start
eas login
echo '{
  "cli": {
    "version": ">= 3.0.0"
  },
  "build": {
    "preview": {
      "distribution": "internal",
      "android": {
        "buildType": "apk"
      }
    },
    "production": {
      "distribution": "store",
      "android": {
        "buildType": "app-bundle"
      },
      "ios": {
        "simulator": false
      }
    }
  },
  "submit": {
    "production": {}
  }
}' > eas.json
eas build -p android --profile preview
eas build -p android --profile preview
eas build -p android --profile production
