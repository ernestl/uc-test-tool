# uc-test-tool
A basic tool to simplify creating and testing Ubuntu Core PC images with configurable essential snaps.

### How to use:
* Clone: `git clone https://github.com/ernestl/uc-test-tool.git`
* Edit `user-config`: Uncomment one of UC16, UC18, UC20, UC22 or UC24 PC image templates
  * Only `Base` field is required
  * Optionally provide specific revisions for essential snaps as required (defaults to latest/stable)
* Run `uc-test-tool`
  * Installs prerequisites
  * Configuration:
    * Loads user configuration
    * Configure Ubuntu One account (once)
    * Logout of snapcraft (once)
    * Login to snapcraft (automatic, except first time and after manual logout)
    * Configure snapcraft assertion signing key (once)
    * Configure Ubuntu One account SSH public key (once)
  * Build PC image
    * Only rebuild on `user-config` change
    * Work happens in `work/` and image ends up in `images/`
    * Images have default size of 3GB (not currently configurable)
  * Run PC image with QEMU
    * Image boots in seperate terminal window named QEMU and additionally creates QEMU graphical window
  * Login over SSH
    * After Ubuntu Core estabishes network connectivity automatic login will create SSH session in a new terminal window
    * Run `snap list` to verify the image content

### Relevant documentation/links:
* https://ubuntu.com/core/docs/create-ubuntu-one
* https://ubuntu.com/core/docs/create-model-assertion
* https://ubuntu.com/core/docs/sign-model-assertion
* https://ubuntu.com/core/docs/custom-images
* https://ubuntu.com/core/docs/use-ubuntu-image
* https://ubuntu.com/core/docs/connect-with-ssh
* https://ubuntu.com/core/docs/testing-with-qemu
* https://github.com/snapcore/models
