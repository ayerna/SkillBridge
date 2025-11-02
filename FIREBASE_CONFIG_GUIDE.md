# Firebase Configuration Guide

This project uses Firebase for authentication, Firestore database, and cloud storage. Follow this guide to configure Firebase using environment variables.

## Environment Variables Setup

All Firebase configuration should be stored as environment variables. This keeps sensitive information secure and allows different configurations for development, staging, and production environments.

### Required Environment Variables

Add these variables to your project. You can set them in the Vercel dashboard under **Settings > Environment Variables**:

\`\`\`
NEXT_PUBLIC_FIREBASE_API_KEY=your_api_key_here
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id
NEXT_PUBLIC_FIREBASE_MEASUREMENT_ID=your_measurement_id
\`\`\`

### Optional Environment Variables

\`\`\`
NEXT_PUBLIC_FIREBASE_MEASUREMENT_ID=your_measurement_id (for Google Analytics)
\`\`\`

## How to Get Firebase Configuration

1. **Go to Firebase Console**: https://console.firebase.google.com/
2. **Select your project**: SkillBridge
3. **Click Project Settings** (gear icon in top left)
4. **Scroll to "Your apps"** section
5. **Select your web app** (should be labeled with your domain)
6. **Copy the Firebase config object**
7. **Map each value to the corresponding environment variable** (see mapping below)

### Mapping Firebase Config to Environment Variables

From your Firebase config object:
\`\`\`javascript
{
  apiKey: "xxx" → NEXT_PUBLIC_FIREBASE_API_KEY
  authDomain: "xxx" → NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN
  projectId: "xxx" → NEXT_PUBLIC_FIREBASE_PROJECT_ID
  storageBucket: "xxx" → NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET
  messagingSenderId: "xxx" → NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID
  appId: "xxx" → NEXT_PUBLIC_FIREBASE_APP_ID
  measurementId: "xxx" → NEXT_PUBLIC_FIREBASE_MEASUREMENT_ID
}
\`\`\`

## Why NEXT_PUBLIC_ Prefix?

Firebase configuration needs to be accessible in the browser (it's public API keys, not secret keys). The `NEXT_PUBLIC_` prefix tells Next.js to expose these variables to the browser safely. They will be embedded in the JavaScript bundle during build time.

## Security Considerations

- Firebase API keys are public and cannot be used to access private data
- Use Firebase Security Rules and Authentication to protect your data
- Never store sensitive server-side keys in `NEXT_PUBLIC_` variables
- For server-side Firebase operations, use environment variables without the `NEXT_PUBLIC_` prefix

## Verification

Once you've added the environment variables:

1. **Local Development**: Restart your dev server with `npm run dev`
2. **After Deployment**: The app will automatically use the Vercel environment variables

If you see console warnings about missing Firebase variables, double-check that all environment variables are correctly named and set in your project.

## Comparison with SendGrid Configuration

Similar to SendGrid API configuration:
- **SendGrid**: Uses `SENDGRID_API_KEY` and `SENDGRID_FROM_EMAIL`
- **Firebase**: Uses multiple `NEXT_PUBLIC_FIREBASE_*` variables for initialization

Both are accessed via `process.env` in the code and validated at runtime with appropriate error messages.
