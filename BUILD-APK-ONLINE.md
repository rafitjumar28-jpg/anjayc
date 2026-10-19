# Build APK online with GitHub Actions (phone only)

## 1. Create a GitHub repository
1. Open https://github.com in your phone browser and sign in or create an account.
2. Tap **+** → **New repository**.
3. Name it `MonetLuaGuard`, choose **Public** or **Private**, then create it.

## 2. Upload this project's files
1. Download and extract `MonetLuaGuard-Android-Source.zip` on your phone.
2. Open your new repository in GitHub.
3. Choose **Add file** → **Upload files**.
4. Upload the *contents* of the `MonetLuaGuard` folder, including the hidden `.github` folder if your file manager shows it. The workflow file must end up at:
   `.github/workflows/build-apk.yml`
5. Commit the uploaded files to the `main` branch.

If your file manager hides dot-folders or GitHub mobile upload does not include `.github`, create the workflow file on GitHub manually:
- Add file → Create new file
- Filename: `.github/workflows/build-apk.yml`
- Paste the contents of `build-apk.yml` from this project
- Commit it.

## 3. Run the build
1. In the repository, open the **Actions** tab.
2. Select **Build MonetLua Guard APK**.
3. If prompted, tap **Run workflow** → choose `main` → **Run workflow**.
4. Wait for the run to finish with a green check mark. If it fails, open the run and inspect the failed step's log.

## 4. Download the APK
1. Open the successful workflow run.
2. Scroll to **Artifacts**.
3. Tap `MonetLuaGuard-debug-apk` to download the ZIP artifact.
4. Extract that downloaded artifact; it contains `app-debug.apk`.
5. Tap the APK to install. Android may ask you to allow installation from that browser/file manager.

## Important
- This creates a **debug APK**, not a Play Store release.
- The APK has not been built or tested until GitHub Actions finishes successfully.
- Keep the repository private if you do not want the source code public.
- The scanner is a basic static pattern scanner; it cannot guarantee that a Lua script is safe.
