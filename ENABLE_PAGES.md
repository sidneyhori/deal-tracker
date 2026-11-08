# Enable GitHub Pages - Manual Steps Required

The dashboard files have been successfully committed to the `main` branch, but GitHub Pages requires manual enablement due to API permission restrictions.

## Quick Steps to Enable Pages

1. **Go to your repository settings**:
   - Visit: https://github.com/sidneyhori/deal-tracker/settings/pages
   - Or: Repository → Settings → Pages (in left sidebar)

2. **Configure Pages source**:
   - Under "Build and deployment"
   - Source: Select **"GitHub Actions"**
   - Click **Save** (if prompted)

3. **Wait for deployment**:
   - The workflow will automatically run
   - Check: https://github.com/sidneyhori/deal-tracker/actions
   - Deployment takes ~30-60 seconds

4. **Verify the site**:
   - Visit: https://sidneyhori.github.io/deal-tracker/
   - Should show the Deal Tracker dashboard

## What's Already Done

✅ `index.html` - Complete dashboard (commit: `451b649`)
✅ `README.md` - Repository description
✅ `.nojekyll` - Prevents Jekyll processing
✅ `.github/workflows/pages.yml` - Automated deployment workflow (commit: `fca51cd`)

All files are committed to `main` and ready to deploy.

## Alternative: Enable via GitHub CLI (if you have admin access)

If you have the GitHub CLI installed with admin permissions:

```bash
gh auth login  # Login with your account
gh api -X POST repos/sidneyhori/deal-tracker/pages \
  -f 'source[branch]=main' \
  -f 'source[path]=/' \
  -f 'build_type=workflow'
```

## Troubleshooting

If the deployment fails after enabling Pages:
- Check Actions tab for error details
- Ensure Pages is set to "GitHub Actions" source (not "Branch")
- Repository must be public or have GitHub Pro for private Pages

---

**Expected URL**: https://sidneyhori.github.io/deal-tracker/
**Repository**: https://github.com/sidneyhori/deal-tracker
