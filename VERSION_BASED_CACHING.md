# 🎯 Smart Version-Based Cache Invalidation

## 🌟 How It Works

Instead of always fetching data or using time-based caching, the app now uses **smart version-based caching**:

1. **App starts** → Checks `version.txt` on GitHub (tiny file, ~5 bytes)
2. **Compares versions:**
   - If version **matches** cached version → Uses cached data (instant load ⚡)
   - If version **changed** → Fetches fresh data from GitHub
3. **Updates cache** with new version number
4. **Next launch** → Repeats the process

---

## ✅ **Benefits:**

| Feature | Version-Based | Always Fetch | Time-Based Cache |
|---------|--------------|--------------|------------------|
| **Speed** | ⚡ Instant (if no changes) | 🐌 1-2 sec every time | ⚡ Instant (until expiry) |
| **Freshness** | ✅ Always up-to-date | ✅ Always up-to-date | ⚠️ Stale until expiry |
| **Network usage** | 📉 Minimal (~5 bytes check) | 📊 ~13 KB every launch | 📉 Minimal |
| **Offline support** | ✅ Yes (uses cache) | ❌ No | ✅ Yes |
| **Control** | ✅ You decide when to update | ❌ No control | ⚠️ Time-based only |

---

## 📝 **How to Update Suggestions:**

### **Step 1: Edit Your Suggestion Files**

Edit any `.txt` files in `suggestions_text/` folder on GitHub:

```
Family - I live with my mum, dad, and siblings
Family - I have a pet dog  ← NEW SUGGESTION
```

### **Step 2: Update version.txt**

**This is the key step!** Edit `version.txt` and increment the version:

**Before:**
```
1.0.0
```

**After:**
```
1.0.1
```

Or use any versioning scheme you like:
- `1.0.0` → `1.0.1` (patch update)
- `1.0.0` → `1.1.0` (minor update)
- `1.0.0` → `2.0.0` (major update)
- `2024-11-11` → `2024-11-12` (date-based)
- `v1` → `v2` (simple increment)

### **Step 3: Commit Changes**

Commit both the suggestion file changes AND the version.txt change.

### **Step 4: Done!**

Next time users launch the app:
- App checks `version.txt`
- Sees version changed from `1.0.0` to `1.0.1`
- Automatically fetches fresh data
- Users see new suggestions!

---

## 🎨 **Example Workflow:**

### **Scenario: Adding New Suggestions**

1. **Edit `about.txt` on GitHub:**
   ```
   Family - I have a pet cat named Whiskers  ← NEW
   ```

2. **Edit `version.txt`:**
   ```
   1.0.1  ← Changed from 1.0.0
   ```

3. **Commit with message:** "Added pet suggestion"

4. **User launches app:**
   ```
   🔍 Checking version from GitHub...
   📌 Remote version: 1.0.1
   📌 Cached version: 1.0.0
   🔄 Version mismatch - cache needs refresh
   🌐 Fetching about.txt from GitHub...
   ✅ Fetched about.txt
   ... (fetches all files)
   🎉 Successfully loaded 13 categories from GitHub
   ```

5. **User launches app again (no changes):**
   ```
   🔍 Checking version from GitHub...
   📌 Remote version: 1.0.1
   📌 Cached version: 1.0.1
   ✅ Version matches - cache is valid
   📦 Loaded all data from cache
   ✅ Remote suggestions loaded successfully
   ```
   **Instant load!** ⚡

---

## 🔄 **Version Numbering Schemes:**

Choose what works best for you:

### **Semantic Versioning (Recommended):**
```
1.0.0 → 1.0.1 → 1.0.2 (small changes)
1.0.0 → 1.1.0 → 1.2.0 (medium changes)
1.0.0 → 2.0.0 → 3.0.0 (major changes)
```

### **Date-Based:**
```
2024-11-11
2024-11-12
2024-11-13
```

### **Simple Increment:**
```
1
2
3
```

### **Named Versions:**
```
v1
v2
v3
```

**Any change to the version string triggers a refresh!**

---

## 📊 **What Gets Checked:**

### **Every App Launch:**
- ✅ Fetches `version.txt` (~5 bytes, super fast)
- ✅ Compares with cached version
- ✅ Decides: use cache or fetch fresh

### **Only When Version Changes:**
- 📥 Fetches all 13 `.txt` files (~13 KB total)
- 💾 Updates cache
- 💾 Saves new version number

---

## 🎯 **Best Practices:**

### **✅ DO:**
- Update `version.txt` every time you change suggestions
- Use consistent version numbering
- Commit version.txt with your changes
- Test by checking console output

### **❌ DON'T:**
- Forget to update `version.txt` (changes won't be detected!)
- Use the same version number twice
- Delete `version.txt` (app will always fetch)

---

## 🔍 **Console Output Examples:**

### **First Launch (No Cache):**
```
🚀 Loading remote suggestions...
🔄 Starting to fetch suggestions from GitHub...
📍 Base URL: https://raw.githubusercontent.com/webappcreator/passport-suggestions/main/suggestions_text
🔍 Checking version from GitHub...
📌 Remote version: 1.0.0
📌 Cached version: none
🔄 Version mismatch - cache needs refresh
🌐 Fetching about.txt from GitHub...
   Status: 200
   Body length: 789 characters
✅ Fetched about.txt - parsed 4 categories
... (all files)
🎉 Successfully loaded 13 categories from GitHub
✅ Remote suggestions loaded successfully
```

### **Second Launch (Cache Valid):**
```
🚀 Loading remote suggestions...
🔄 Starting to fetch suggestions from GitHub...
📍 Base URL: https://raw.githubusercontent.com/webappcreator/passport-suggestions/main/suggestions_text
🔍 Checking version from GitHub...
📌 Remote version: 1.0.0
📌 Cached version: 1.0.0
✅ Version matches - cache is valid
✅ Cache is up-to-date, using cached data
📦 Loaded all data from cache
✅ Remote suggestions loaded successfully
```

### **After Version Update:**
```
🚀 Loading remote suggestions...
🔄 Starting to fetch suggestions from GitHub...
📍 Base URL: https://raw.githubusercontent.com/webappcreator/passport-suggestions/main/suggestions_text
🔍 Checking version from GitHub...
📌 Remote version: 1.0.1  ← Changed!
📌 Cached version: 1.0.0
🔄 Version mismatch - cache needs refresh
🔄 Version changed, invalidating cache and fetching fresh data
🌐 Fetching about.txt from GitHub...
... (fetches all files)
🎉 Successfully loaded 13 categories from GitHub
✅ Remote suggestions loaded successfully
```

---

## 🆘 **Troubleshooting:**

### **Problem: Changes not showing up**

**Cause:** Forgot to update `version.txt`

**Solution:**
1. Go to GitHub
2. Edit `version.txt`
3. Change version number (e.g., `1.0.0` → `1.0.1`)
4. Commit changes
5. Restart app

### **Problem: Always fetching (never using cache)**

**Cause:** `version.txt` doesn't exist or keeps changing

**Solution:**
1. Make sure `version.txt` exists in repository root
2. Check console for version numbers
3. Make sure version.txt contains just the version (e.g., `1.0.0`)

### **Problem: Version check fails**

**Cause:** Network issue or wrong URL

**Solution:**
- App will use cached data (safe fallback)
- Check internet connection
- Verify `version.txt` exists at:
  ```
  https://raw.githubusercontent.com/webappcreator/passport-suggestions/main/version.txt
  ```

---

## 📁 **File Structure on GitHub:**

```
passport-suggestions/
├── version.txt  ← IMPORTANT: Update this when you change suggestions!
├── README.md
└── suggestions_text/
    ├── about.txt
    ├── sensitivities.txt
    ├── interests_home.txt
    └── ... (all other .txt files)
```

---

## 🎉 **Summary:**

**This is the best of all worlds:**

✅ **Fast** - Instant load when no changes  
✅ **Fresh** - Always up-to-date when you update  
✅ **Efficient** - Minimal network usage  
✅ **Offline** - Works without internet (uses cache)  
✅ **Controlled** - You decide when to update  
✅ **Simple** - Just increment version.txt  

**Just remember: Update `version.txt` whenever you change suggestions!** 🎯

