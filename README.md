# Communication Passport - Suggestions Database

Simple text files containing suggestions for the Communication Passport mobile app.

## 📝 Super Simple Format

Each file contains suggestions in this format:

```
Category Name - Suggestion text
```

**That's it!** No JSON, no complicated syntax - just plain text.

## 📂 Files

All suggestion files are in the `suggestions_text` folder:

- `about.txt` - Personal info, family, personality, food, routines
- `sensitivities.txt` - Tactile, auditory, visual, olfactory, environmental
- `interests_home.txt` - Toys, play, physical activities, sensory
- `interests_school.txt` - Music, learning, creative activities
- `communication_how.txt` - Verbal, non-verbal, learning styles
- `communication_support.txt` - Processing time, language strategies
- `communication_upset.txt` - Emotional responses, seeking support
- `communication_calm.txt` - Auditory calming, physical comfort
- `communication_happy.txt` - Physical expressions, vocal and social
- `learning.txt` - Visual, auditory, strategies, development areas
- `needs_help.txt` - Communication, motor skills, transitions, social
- `strengths.txt` - Personality traits, learning and skills
- `goals.txt` - Communication, motor, social, emotional, cognitive

## ✏️ How to Edit

### **Quick Edit (GitHub Web):**

1. Click on `suggestions_text` folder
2. Click on any `.txt` file
3. Click the **pencil icon** (✏️)
4. Make your changes
5. Click "Commit changes"
6. **Done!** The app will use the new suggestions

### **Format Rules:**

```
Category Name - Suggestion text
```

- Use ` - ` (space-dash-space) to separate category from suggestion
- One suggestion per line
- Empty lines are ignored (use them to organize)
- Lines starting with `#` are comments (ignored)

### **Example:**

```
# Family-related suggestions
Family - I live with my mum, dad, and siblings
Family - My grandparents live nearby
Family - I am close to my extended family

# Personality traits
Personality - I am friendly and have a good sense of humour
Personality - I am very calm, kind, and trusting
```

## ➕ Adding New Suggestions

### **To add to existing category:**

Just add a new line with the same category name:

```
Family - I live with my mum, dad, and siblings
Family - My grandparents live nearby
Family - I have a pet dog  ← NEW
```

### **To create new category:**

Add a line with a new category name:

```
Family - I live with my mum, dad, and siblings
Pets - I have a dog named Max  ← NEW CATEGORY
Pets - I love playing with my cat  ← NEW CATEGORY
```

## 📱 Mobile Editing

You can edit these files on your phone:

1. Open GitHub app or mobile website
2. Navigate to this repository
3. Open `suggestions_text` folder
4. Tap any file
5. Tap the pencil icon
6. Edit and commit

**Perfect for quick updates on the go!**

## ✅ Good Examples

```
Family - I live with my mum, dad, and siblings
Personality - I am friendly and have a good sense of humour
Food & Diet - My favourite food is popcorn
Routines & Preferences - I love routines

# You can add comments like this
# Empty lines are fine too

Sensory - I love water play (but don't like wet clothes)
```

## ❌ Bad Examples

```
❌ Family-I live with my mum (no spaces around -)
❌ I live with my mum (missing category name)
❌ Family (missing suggestion text)
```

## 🔄 How Updates Work

1. You edit a `.txt` file on GitHub
2. Commit your changes
3. The app automatically fetches updates:
   - On next app restart
   - After 24 hours (cache expiry)

## 💡 Tips

1. **Use comments** (`#`) to organize sections
2. **Use empty lines** to make files readable
3. **Keep category names consistent** within each file
4. **Test your changes** by viewing the raw file URL
5. **Start small** - Edit one file first to test

## 🧪 Testing

To test if your files are accessible:

1. Click on a `.txt` file
2. Click the "Raw" button
3. Copy the URL (should look like):
   ```
   https://raw.githubusercontent.com/webappcreator/passport-suggestions/main/suggestions_text/about.txt
   ```
4. Open in browser - you should see plain text

## 📊 File Structure

```
passport-suggestions/
├── README.md (this file)
└── suggestions_text/
    ├── about.txt
    ├── sensitivities.txt
    ├── interests_home.txt
    ├── interests_school.txt
    ├── communication_how.txt
    ├── communication_support.txt
    ├── communication_upset.txt
    ├── communication_calm.txt
    ├── communication_happy.txt
    ├── learning.txt
    ├── needs_help.txt
    ├── strengths.txt
    └── goals.txt
```

## 🎯 Why Text Files?

✅ **Super simple** - No syntax to learn  
✅ **Hard to break** - Very forgiving format  
✅ **Mobile-friendly** - Easy to edit on phone  
✅ **Comments supported** - Document your suggestions  
✅ **Human-readable** - Anyone can understand  

## 🤝 Contributing

If multiple people are editing:

1. Always check for latest changes before editing
2. Add descriptive commit messages
3. Use comments to explain changes
4. Test the raw URL after committing

## ⚠️ Important

- **Don't rename files** - The app expects specific file names
- **Don't move files** - They must be in `suggestions_text` folder
- **Keep the format** - Always use `Category - Suggestion`
- **Use spaces** - Around the `-` separator

## 📞 Need Help?

If suggestions aren't showing in the app:

1. Check the file format: `Category - Suggestion`
2. Make sure files are in `suggestions_text` folder
3. Verify file names are exactly as listed above
4. Test the raw GitHub URL in your browser
5. Check for typos in category names

---

**Last Updated:** 2025-11-11  
**Format Version:** 1.0 (Text Files)

**Happy editing! 📝**

