# Craft a commit message for the tag.
- [ ] LASTTAG='v0.21.2'
- [ ] VERSION='0.21.3'
- [ ] NEWTAG="v${VERSION}"
- [ ] Release notes for the new tag
```bash 
cat <<EOF > release-notes.txt
This is release ${NEWTAG} of console-login-helper-messages.

Thanks to the following contributors for patches during this release: 

$(git shortlog --no-merges --pretty=format:"%h %s" -e ${LASTTAG}..HEAD)
EOF
```
# After crafting message then create the tag
- [ ] git tag --file release-notes.txt -s ${NEWTAG}

# After creating the tag view it and verify signature:
- [ ] git show ${NEWTAG}
- [ ] git tag --verify ${NEWTAG}

# and push it to the remote (not a fork)
- [ ] git push --tags 

# Update release notes on the GitHub web interface
