# figma-make-poc

Benign marker repository used for an **authorized security test** of Figma Desktop's
Make-Local handoff/clone flow (reported to Figma's bug bounty program).

When the Figma Desktop Make-Local flow clones this repository into a folder the tester
trusts, the `.figma/make/{setup,install,dev,verify}` scripts run as the logged-in user.
They only:

- append a line to `~/figma-make-poc/evidence.log`
- write `setup.marker` / `install.marker` / `dev.marker` / `verify.marker` in the cloned folder
- write `PWNED_BY_SETUP.txt` in the cloned folder

No network access, no persistence, no data collection. The tester owns both the machine and
the repository, and the test is limited to their own environment.
