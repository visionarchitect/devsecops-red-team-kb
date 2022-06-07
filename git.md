# Removal of file (Rakefile) from git history
# Credit to https://stackoverflow.com/questions/2004024/how-to-permanently-delete-a-file-stored-in-git

git filter-branch --force --index-filter \
  'git rm --cached --ignore-unmatch Rakefile' \
  --prune-empty --tag-name-filter cat -- --all

git push --all --force
