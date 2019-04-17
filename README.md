# dreamcast-vmu-icons
Recovery and restoration of dcvmuicons.net, a Dreamcast web browser site for downloading memory card icons.

#### How To Host VMI/VMS
Dreamcast VMU files end with a `.VMS` file extension, for example `ICONDATA.VMS`. In order to be able to download these files using the Dreamcast web browser you will need a matching VMS info file, aka `.VMI`, for example `ICONDATA.VMI` in the same folder. These VMI files point the Dreamcast web browser to download the VMS file.

Luckily the [NeoDC-Icondata-Tool](https://github.com/mrneo240/NeoDC-Icondata-Tool) generates the `ICONDATA.VMI` file along with the icon VMS file. The last piece of the puzzle is having your web server serve up the file as the correct MIME type. I was able to achieve this on my Apache server by including an `.htaccess` file with the following lines:

```
addtype application/x-dreamcast-vms-info vmi
addtype application/x-dreamcast-vms vms
```
More details can be found at [vmudev.dcemulation.org](http://vmudev.dcemulation.org/faq.html#QUESTION6.1.2).

#### Thank You! 🙏
- [SegaRetro](https://segaretro.org) for maintaining an archive of the original website itself after all these years.
- [@mrneo240](https://github.com/mrneo240) for creating [NeoDC-Icondata-Tool](https://github.com/mrneo240/NeoDC-Icondata-Tool), 
which was used to rebuild the lost 326 VMI/VMS data files.
