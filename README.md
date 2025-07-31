Kali Linux for <img width="107" height="38" alt="logo" src="https://github.com/user-attachments/assets/667ffdbf-ea10-4c9c-817a-09cd85f41fe3" />

<img width="660" height="468" alt="pi5-plus-5" src="https://github.com/user-attachments/assets/482b8d27-8aa1-4954-95f9-4c072fea275a" />


I am creating this repository because it feels like support for my new Orange Pi 5 Plus is severely lacking compared to the Raspberry Pi.

PLEASE FEEL FREE to add images for your Orange Pi device or make suggestions to what is already here!

I am building Kali Rolling Releases for each desktop environment as well as a CLI version using the official [Kali ARM build script](https://www.kali.org/docs/development/arm-build-scripts/).

<img width="144" height="144" alt="download-orange-pi-os" src="https://github.com/user-attachments/assets/82b10acf-7b32-4017-9369-c41289b1c0a9" /><img width="225" height="225" alt="Kali-ARM-Chip" src="https://github.com/user-attachments/assets/526796c1-f7f5-4889-a45f-247c31a782cc" />

   
To ensure swap is enabled after reboot, add it to /etc/fstab:

echo '/swapfile swap swap defaults 0 0' | sudo tee -a /etc/fstab

That’s it!
You have enabled swap on Kali Linux, and it will persist after reboot if you completed step 7. If you ever want to remove the swap, simply reverse these steps by disabling swap (sudo swapoff /swapfile), removing the /swapfile entry from /etc/fstab, and deleting the file.
