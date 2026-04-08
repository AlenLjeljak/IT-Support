Problem 1: User cannot log in to domain

1. Verify username and password — Ensure correct credentials are used.
2. Check Caps Lock and keyboard layout — Prevent input errors.
3. Check if account is locked — Too many failed attempts may lock account.
4. Unlock account in Active Directory — Restore access.
5. Reset password — Ensure user has correct credentials.
6. Check account status — Ensure account is enabled.
7. Verify domain connection — Device must be connected to domain network/VPN.
8. Test login on another device — Helps isolate device vs account issue.
9. Check time sync — Incorrect system time can block authentication.
10. Escalate — If domain controller issues suspected.

---

Problem 2: Account locked out repeatedly

1. Unlock account — Restore access temporarily.
2. Check lockout source — Use Event Viewer or logs.
3. Ask user about multiple devices — Old passwords may be cached.
4. Check saved credentials — Outlook, VPN, mapped drives.
5. Log out from all sessions — Prevent background login attempts.
6. Reset password — Ensure new credentials everywhere.
7. Check mobile devices — Email apps often cause lockouts.
8. Monitor lockout events — Identify repeating pattern.
9. Inform user — Explain root cause.
10. Escalate — If lockout source unclear.

---

Problem 3: User cannot access shared folder

1. Verify network connection — Required for domain resources.
2. Check user permissions — NTFS + Share permissions.
3. Add user to correct security group — Access often group-based.
4. Log out/in — Refresh token and permissions.
5. Run `gpupdate /force` — Apply latest policies.
6. Test access via UNC path — e.g. \server\folder
7. Check group membership — Ensure correct groups assigned.
8. Verify folder path — Ensure correct resource.
9. Test another user — Helps isolate permission issue.
10. Escalate — If permissions appear correct but still failing.

---

Problem 4: Password reset not working

1. Reset password in AD — Ensure correct procedure.
2. Confirm password policy — Length, complexity, history.
3. Ensure replication — Changes may take time across DCs.
4. Unlock account — Reset may not unlock automatically.
5. Ask user to wait 1–2 minutes — Sync delay.
6. Verify login domain — Correct domain must be used.
7. Clear cached credentials — Prevent old password reuse.
8. Restart device — Refresh authentication.
9. Test on another device — Isolate issue.
10. Escalate — If replication issues suspected.

---

Problem 5: User not receiving group permissions

1. Add user to correct group — Assign access.
2. Verify group type — Security vs Distribution.
3. Log out/in — Refresh access token.
4. Run `gpupdate /force` — Apply group policy.
5. Check nested groups — Ensure correct structure.
6. Verify replication — Changes may not be synced.
7. Check token size — Too many groups can cause issues.
8. Test access manually — Confirm permissions applied.
9. Check domain controller — Which DC handled login.
10. Escalate — If group policy issues suspected.

---

Problem 6: Computer not joined to domain

1. Check network connection — Must reach domain controller.
2. Verify DNS settings — Must point to domain DNS.
3. Try to join domain — System > Join Domain.
4. Enter correct domain credentials — Admin rights required.
5. Check computer name — Must be unique.
6. Restart computer — Required after join.
7. Verify in AD — Ensure computer object exists.
8. Log in with domain account — Test functionality.
9. Check OU placement — Correct policies applied.
10. Escalate — If domain join fails repeatedly.

---

Problem 7: Group Policy not applying

1. Run `gpupdate /force` — Force policy update.
2. Restart computer — Some policies require reboot.
3. Check OU placement — Policies linked to OU.
4. Verify user/computer location — Must be correct OU.
5. Run `gpresult /r` — See applied policies.
6. Check security filtering — User/group must have access.
7. Check WMI filters — May block policy.
8. Verify replication — GPO changes must sync.
9. Check Event Viewer — Look for policy errors.
10. Escalate — If GPO corruption suspected.

---

Problem 8: User profile not loading

1. Restart computer — Temporary issue may resolve.
2. Log in with another account — Test profile issue.
3. Check profile service — Ensure running.
4. Check disk space — Full disk can block profile load.
5. Rename profile folder — Create new profile.
6. Delete corrupted profile (advanced) — Reset user profile.
7. Check permissions — Profile folder access.
8. Check Event Viewer — Identify error.
9. Test new user account — Isolate issue.
10. Escalate — If profile corruption persists.

---

Problem 9: DNS issues affecting domain login

1. Check DNS settings — Must use domain DNS server.
2. Run `ipconfig /all` — Verify DNS configuration.
3. Ping domain controller — Check connectivity.
4. Run `nslookup domain` — Verify name resolution.
5. Flush DNS cache — `ipconfig /flushdns`
6. Restart network adapter — Reset connection.
7. Restart computer — Refresh settings.
8. Check DHCP settings — Ensure correct DNS assignment.
9. Test another device — Isolate issue.
10. Escalate — If DNS server issue suspected.

---

Problem 10: User cannot access email (AD-related)

1. Check account status — Ensure active in AD.
2. Verify group membership — Email access may depend on groups.
3. Check password — Reset if needed.
4. Verify sync with Azure AD — Hybrid environments.
5. Check license assignment — Required for mailbox.
6. Test login via web — Helps isolate issue.
7. Check MFA — May block login.
8. Restart Outlook — Refresh connection.
9. Recreate profile — Fix corruption.
10. Escalate — If sync or Exchange issue suspected.
