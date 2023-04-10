# Admin SFDX Engagement
## Process
1. Admin assigned Story 4567.
2. Admin initiates automated process to create and open scratch org.
   1. Start VM with automation image.
   2. Clone git repo.
   3. Create/checkout git branch for Story named, `story-4567`.
   4. Create/checkout git branch for supporting work, `story-4567-admin`.
   5. Connect to devhub.
   6. Create scratch org, per project configuration.
   7. Push metadata to scratch org with `sfdx source:push`.
   8. Record the scratch org information by executing `sfdx org:diplay --json --verbose` while directing the result to a text file in `./config/`.
   9. Commit/push the entire working project directory to the git host with `git add -f .`, commit and push.
   10. Terminate VM.
3.  Admin works Story to completion, in scratch org.
4.  Admin initiates automated process to capture changed metadata.
    1. Start VM with automation image.
    2. Clone git repo.
    3. Checkout git branch for supporting work.
    4. Connect to devhub.
    5. Connect to scratch org via recorded scratch org information via `sfdx org:login:sfdx-url -f ./config/???`.
    6. Capture changed metadata with `sfdx source:pull`.
    7. Commit and merge `./sfdx-source/` changes, only, into parent branch, `story-4567`.
       1. `git checkout story-4567`
       2. `git checkout story-4567-admin -- ./sfdx-source`
       3. `git commit -m "..." && git push`
    8. Create PR for story branch to its parent.
    9.  Terminate VM.
 5. PR reviewers assess changes, with particular attention to excluding source-tracking noise.
 6. Approve and merge PR.
 7. Advance Story status.