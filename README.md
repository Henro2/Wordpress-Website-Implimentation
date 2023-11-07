**IMPLIMENTING WORDPRESS WEBSITE WITH LVM STORAGE MANAGEMENT**

1. I unched EC2 redheart linux instance called **Web-serverRH**

     ![Alt text](Images/redheartinstance.png)


 2.  I created 3 volumes with 10gb of storage each on the same availability zone with my Redhat Webserver.


      ![Alt text](Images/createdvolumes.png)



 3. I attached the 3 volumes one by one to my redhat instance


   
   
     ![Alt text](Images/attachedvolumes.png)
4. .     With termiux ssh client, I connected successfully to my redhat instance and updated it using the comand **sudo yum update** 



     ![Alt text](Images/conectedupdatedredhat.png)



5. I used lSBlK commad to inspect the blocks that are attached to my server 

   ![Alt text](Images/blocksinspect.png)

6.  I used df -h to see all the mouts and free space

    ![Alt text](Images/df-h.png)


7.  I used **gdisk** utility to create a single partition on the 3 volumes i created with name sudo xvdf xvdg xvdh


     ![Alt text](Images/writedparti.png)


8.  I now used lsbkl command to view my newly configured partitions.

     ![Alt text](Images/lsblk.png)



9.  I installed Lvm2 package using the command **sudo yum install lvm2 -y**


      
     ![Alt text](Images/lvm2install.png)


10.  I now use pvcreate the mark all the 3 disk as physical volumes to be used by lvm

     ![Alt text](Images/pvcreate.png)



11. I used command **sudo pvs** to see that the 3 physical volumes have been successfully created 

     ![Alt text](Images/volumessucess.png)


12. I now used VGcreate to add all the PVs to a volume group and giving the VG name as webdata-vg

     ![Alt text](Images/Vggroup.png)



13.  I used sudo vgs command to varify that VG was create successfully.

      ![Alt text](Images/varifyvg.png)


14.  



    

