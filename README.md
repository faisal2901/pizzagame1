# Pizza Empire

A mobile pizza-shop game for up to 4 players online, starring Atiya, Arisha, Faisal and Azaan.

- **Empire** – build one shop together: tables, ovens, staff, deliveries, star rating, day/night service, live challenges, six city branches.
- **Pizza Battle** – a 4-minute race in the same shop. Every action scores points, live challenges pay bonuses, empty spots are filled by bots.

Everything is in `index.html` (no build step). Online play uses WebRTC through the free PeerJS server, so phones can be on different Wi-Fi or mobile networks.

## 1. Put it online (link anyone can open)

**Vercel (recommended)**
1. Create a new GitHub repository and upload everything in this folder (keep the `.github` folder).
2. On vercel.com: *Add New → Project → Import* that repository.
3. Framework preset: **Other**. Leave build command and output directory empty. Click **Deploy**.
4. Share the `https://…vercel.app` link with the family.

**GitHub Pages (alternative)**: repository *Settings → Pages → Deploy from a branch → main / (root)*.

On each phone, open the link once and choose **Install on this phone** (Android, Chrome) or *Share → Add to Home Screen* (iPhone, Safari). It then opens full screen from its own icon.

## 2. Get the Android APK (no Android Studio needed)

1. Push this folder to GitHub (same repository as above is fine).
2. Open the repository's **Actions** tab. The *Build Android APK* workflow runs on every push to `main` (or press **Run workflow**).
3. When it finishes (about 5–8 minutes), open the run and download **PizzaEmpire-APK** under *Artifacts*. Unzip it to get `app-debug.apk`.
4. Send the APK to each Android phone, open it, and allow *Install unknown apps* when asked.

The APK is a debug build: fine for family installs, not for the Play Store. For a Play Store release you need a signed release build (`./gradlew bundleRelease` with your keystore), or use pwabuilder.com with your Vercel link.

iPhones cannot install APKs; use the web link + Add to Home Screen.

## 3. Playing online
1. One player taps **Create online shop** (Empire tab) or **Create battle room** (Battle tab) and reads out the 4-letter code.
2. Others pick their character, type the code, and tap **Join room**.
3. The host's phone runs the shop and saves Empire progress, so the host should keep the game open. If the host leaves, everyone gets a message and can start a new room.

If a phone can't connect on mobile data, try Wi-Fi: a few networks block peer-to-peer connections.
