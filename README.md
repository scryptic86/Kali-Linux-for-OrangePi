Kali Linux for <img width="107" height="38" alt="logo" src="https://github.com/user-attachments/assets/667ffdbf-ea10-4c9c-817a-09cd85f41fe3" />

<img width="660" height="468" alt="pi5-plus-5" src="https://github.com/user-attachments/assets/482b8d27-8aa1-4954-95f9-4c072fea275a" />


I am creating this repository because it feels like support for my new Orange Pi 5 Plus is severely lacking compared to the Raspberry Pi.

I am building Kali Rolling Releases for each desktop environment as well as a CLI version using the official [Kali ARM build script](https://www.kali.org/docs/development/arm-build-scripts/).

<img width="144" height="144" alt="download-orange-pi-os" src="https://github.com/user-attachments/assets/82b10acf-7b32-4017-9369-c41289b1c0a9" />![kali-everywhere-arm](https://github.com/user-attachments/assets/6c5a7f9d-9006-4996-b870-2c253c044b99)#


These images were built with Swap DISABLED. I'm sure most of you know how to enable it if needed but here is a quick step-by-step just in case.(I cheated with A.I. ;))

Here’s an easy, step-by-step procedure to enable swap on Kali Linux using a swap file. This method works on most modern systems and does not require repartitioning your disk.

1. Check Existing Swap
Open a terminal and run:

swapon --show
or
free -h

If nothing is listed under swap, you currently have no swap enabled.

3. Create a Swap File
Decide how much swap you want (e.g., 2G for 2 gigabytes):

sudo fallocate -l 2G /swapfile

If fallocate is unavailable, use:

sudo dd if=/dev/zero of=/swapfile bs=1M count=2048

3. Set Correct Permissions
For security, restrict access to root:

sudo chmod 600 /swapfile

4. Format the File as Swap

sudo mkswap /swapfile

5. Enable the Swap File

sudo swapon /swapfile

6. Verify Swap Is Active
   
swapon --show
free -h

You should now see the swap file listed and the swap total increased.

7. Make Swap Permanent (Optional but Recommended)
   
To ensure swap is enabled after reboot, add it to /etc/fstab:

echo '/swapfile swap swap defaults 0 0' | sudo tee -a /etc/fstab

That’s it!
You have enabled swap on Kali Linux, and it will persist after reboot if you completed step 7. If you ever want to remove the swap, simply reverse these steps by disabling swap (sudo swapoff /swapfile), removing the /swapfile entry from /etc/fstab, and deleting the file.
