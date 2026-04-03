# Testing the Gemini CLI Plugin

## ✅ Setup Complete

The test marketplace has been created at:
```
/Users/vinayak/Documents/test-marketplace/
```

A test project has been created at:
```
/Users/vinayak/Documents/test-plugin-project/
```

## 🧪 Step-by-Step Testing

### Step 1: Add the Test Marketplace

In Gemini CLI (this chat), run:

```
/plugin marketplace add /Users/vinayak/Documents/test-marketplace
```

Expected output: Confirmation that the marketplace was added.

### Step 2: List Available Plugins

```
/plugin marketplace list
```

Expected output: Should show `gemini-scientific-writer` in the test-marketplace.

### Step 3: Install the Plugin

```
/plugin install gemini-scientific-writer@test-marketplace
```

Expected output: Plugin installation confirmation, possibly a prompt to restart.

### Step 4: Restart Gemini CLI (if prompted)

If Gemini CLI asks you to restart, do so now.

### Step 5: Open the Test Project

Open the test project directory in Gemini CLI:
```
/Users/vinayak/Documents/test-plugin-project/
```

Or use Cursor's "Open Folder" and navigate to this directory.

### Step 6: Run the Init Command

In the test project, run:

```
/scientific-writer:init
```

Expected behavior:
- Should check for existing GEMINI.md (there isn't one)
- Should create a new GEMINI.md file
- Should display a comprehensive onboarding message
- The GEMINI.md file should appear in the test project directory

### Step 7: Verify Skills Are Available

Ask Gemini:

```
What skills are available?
```

Expected output: Should list the scientific writing skills, including:
- research-lookup
- peer-review
- citation-management
- clinical-reports
- research-grants
- scientific-slides
- And 13 more...

### Step 8: Test Basic Functionality

Try a simple task:

```
Create a short scientific abstract (150 words) on quantum computing applications.
```

Expected behavior:
- Gemini should use the scientific-writing skill
- Should create a properly formatted abstract
- May use research-lookup if configured

### Step 9: Verify GEMINI.md Content

Open the created GEMINI.md file and verify:
- [ ] File exists at `/Users/vinayak/Documents/test-plugin-project/GEMINI.md`
- [ ] Contains "Gemini Agent System Instructions" header
- [ ] Has the plugin comment at the top
- [ ] Contains comprehensive scientific writing instructions
- [ ] Includes workflow protocols, citation policies, etc.

## 🔍 Troubleshooting

### Plugin Not Found
If the plugin isn't found:
1. Check marketplace path is correct: `/Users/vinayak/Documents/test-marketplace`
2. Verify marketplace.json exists and is valid JSON
3. Try removing and re-adding: `/plugin marketplace remove test-marketplace`

### Skills Not Showing
If skills aren't available:
1. Check that `skills/` directory exists in the plugin
2. Verify each SKILL.md has valid YAML frontmatter
3. Try reinstalling the plugin

### Init Command Not Working
If `/scientific-writer:init` doesn't work:
1. Check that `commands/scientific-writer-init.md` exists
2. Verify the YAML frontmatter in the command file
3. Check that `templates/GEMINI.scientific-writer.md` exists

### Template Not Found
If init command can't find the template:
1. Verify `/Users/vinayak/Documents/gemini-scientific-writer/templates/GEMINI.scientific-writer.md` exists
2. Check file permissions
3. Try using absolute path in the plugin

## 📊 Verification Checklist

After completing all steps:

- [ ] Test marketplace added successfully
- [ ] Plugin visible in marketplace list
- [ ] Plugin installed without errors
- [ ] `/scientific-writer:init` command executed successfully
- [ ] GEMINI.md created in test project
- [ ] Skills query returns scientific writing skills
- [ ] Can create a simple scientific document
- [ ] Plugin works as expected

## 🎯 Success Criteria

The plugin is working correctly if:

1. **Installation succeeds** - No errors during marketplace add or plugin install
2. **Command works** - `/scientific-writer:init` creates GEMINI.md
3. **Skills available** - "What skills are available?" shows 19 skills
4. **Functional** - Can create scientific content using the skills
5. **Template correct** - GEMINI.md contains full scientific writing instructions

## 📝 Notes

- The `.gemini/` directory in the plugin repo is for development only
- The plugin uses `skills/`, `commands/`, and `templates/` directories
- Users can customize their GEMINI.md after initialization
- Skills are available project-wide once plugin is installed

## 🚀 Next Steps After Successful Test

If everything works:
1. Update version in `.gemini-plugin/plugin.json` if needed
2. Commit and push changes to GitHub
3. Consider publishing to a public marketplace
4. Update documentation with real-world usage examples

---

**Ready to test?** Start with Step 1 above! 🧪

