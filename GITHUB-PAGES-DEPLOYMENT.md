# GitHub Pages Deployment Guide

## Quick Fix for Current Error

The build error you're seeing is likely due to GitHub trying to process your site with Jekyll. Here's how to fix it:

### Step 1: Add .nojekyll File
1. In your repository root, create a file named `.nojekyll` (no extension)
2. Leave it empty
3. Commit and push

This tells GitHub Pages to skip Jekyll processing and serve your files directly.

### Step 2: Verify File Structure
Your repository should look like this:
```
your-repo/
├── .nojekyll          (empty file - IMPORTANT!)
├── index.html         (your main website file)
├── misha-photo.jpg    (your photo)
├── README.md          (optional - repository description)
└── SECURITY-DOCUMENTATION.md (optional - documentation)
```

### Step 3: GitHub Pages Settings
1. Go to your repository on GitHub
2. Click "Settings"
3. Scroll to "Pages" section (left sidebar)
4. Under "Source", select:
   - Branch: `main` (or `master`)
   - Folder: `/ (root)`
5. Click "Save"
6. Wait 1-2 minutes for deployment

### Step 4: Access Your Site
Your site will be available at:
- `https://[your-username].github.io/[repo-name]/`

Example: `https://mishamorozov.github.io/therapy-website/`

## Common Issues & Solutions

### Issue 1: 404 Error After Deployment
**Solution**: 
- Ensure `index.html` is in the root directory
- Check that `.nojekyll` file exists
- Wait a few minutes after pushing changes

### Issue 2: Build Failed / Red X
**Solution**:
- Add `.nojekyll` file to root
- Make sure all files are properly committed
- Check file names are correct (case-sensitive)

### Issue 3: Image Not Loading
**Solution**:
- Make sure `misha-photo.jpg` is in the same directory as `index.html`
- Check the image reference in HTML: `<img src="misha-photo.jpg">`
- Verify the file was uploaded to GitHub

### Issue 4: Form Not Working
**Solution**:
- The Web3Forms API key is already configured
- Test the form after deployment
- Check browser console for errors

## File Size Limits (Free Tier)

GitHub Pages Free Tier Limits:
- ✅ Repository size: Up to 1 GB
- ✅ Published site size: Up to 1 GB
- ✅ Bandwidth: 100 GB/month
- ✅ Builds: 10 per hour

Your current files:
- index.html: ~75 KB ✅
- misha-photo.jpg: ~97 KB ✅
- Total: ~172 KB ✅ (Well within limits!)

## Step-by-Step Upload Process

### If Starting Fresh:
1. Create new repository on GitHub
2. Name it (e.g., "therapy-website")
3. Initialize with README (optional)
4. Upload these files:
   - `.nojekyll` (create as new file)
   - `index.html`
   - `misha-photo.jpg`
5. Go to Settings → Pages
6. Select source: main branch, / (root)
7. Save and wait

### If Updating Existing Repository:
1. Delete any `_config.yml` file if present
2. Add `.nojekyll` file to root
3. Ensure `index.html` and `misha-photo.jpg` are in root
4. Commit all changes
5. Push to GitHub
6. Wait 1-2 minutes

## Verification Checklist

After deployment, verify:
- [ ] Site loads at GitHub Pages URL
- [ ] All 4 languages work (EN, DA, UK, RU)
- [ ] Photo displays correctly
- [ ] Navigation works
- [ ] Form submission works
- [ ] Mobile responsive design works
- [ ] All sections visible

## Custom Domain (Optional)

If you want to use your own domain (e.g., mishamorozov.com):

1. Create a file named `CNAME` (no extension)
2. Add your domain name: `mishamorozov.com`
3. Commit and push
4. In your domain registrar, add DNS records:
   - Type: A
   - Name: @
   - Value: GitHub Pages IPs:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
5. Add CNAME record:
   - Type: CNAME
   - Name: www
   - Value: [your-username].github.io

6. In GitHub Settings → Pages, add custom domain
7. Wait 24-48 hours for DNS propagation

## Security Notes

- HTTPS is automatically enabled by GitHub Pages
- All security headers from the HTML will work
- Form submissions go through Web3Forms (secure)
- No server-side configuration needed

## Troubleshooting Commands

### Check GitHub Pages Status:
1. Go to your repo
2. Click "Actions" tab (if available)
3. Look for deployment status

### Force Rebuild:
1. Make a small change (add space to README)
2. Commit and push
3. This triggers a new build

### Clear Cache:
- Press Ctrl+Shift+R (Windows/Linux)
- Press Cmd+Shift+R (Mac)
- Or open in incognito/private mode

## Support

If issues persist:
1. Check GitHub Pages status: https://www.githubstatus.com/
2. Review GitHub Pages documentation: https://docs.github.com/pages
3. Check repository Actions tab for error details

## Performance Tips

To keep your site fast (already optimized):
- ✅ Minimized file sizes
- ✅ Optimized image
- ✅ No external dependencies
- ✅ Inline CSS and JavaScript

Your site should load in under 1 second!

---
**Quick Summary for Your Error:**
1. Add `.nojekyll` file (empty) to repository root
2. Commit and push
3. Wait 2 minutes
4. Your site will work!

The `.nojekyll` file is the most common solution for build errors on GitHub Pages.
