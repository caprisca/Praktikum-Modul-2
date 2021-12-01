

# **Praktikum Modul 2**

#### **By : Rasyid Sabilillah & Catharina Prisca**





1. 

   * Cek lxc dengan menggunakan 

   ```markdown
    lxc-ls -f
   ```

   * Hapus ubuntu landing dengan menggunakan  command seperti dibawah ini, dan buat ubuntu focal baru dengan lxc-create

   ```markdown
    lxc-destroy ubuntu_landing
   ```

   ![](C:\Users\Catharina Prisca\Downloads\1\2021-11-17.png)

   ![](C:\Users\Catharina Prisca\Downloads\1\2021-11-17_1.png)

​		

- Setelah membuat baru, gunakan command lxc-start untuk memulai ubuntu_landing dan gunakan command lxc-attach untuk membuka ubuntu_landing. Lalu gunakan install nano untuk mengedit config.

  ​			![](C:\Users\Catharina Prisca\Downloads\1\2021-11-17_2.png)			

  

  -  Atur IP ubuntu_landing

  ![](C:\Users\Catharina Prisca\Downloads\1\2021-11-17_3.png)
  ​	Dengan menggunakan 

  ```markdown
  sudo lxc-start -n ubuntu_landing
  sudo lxc-attach  -n ubuntu_landing
  nano /etc/netplan/10-lxc.yaml
  netplan apply
  
  ```

  ![](C:\Users\Catharina Prisca\Downloads\1\2021-11-17_4.png)

  

  - atur autostart lxc, seperti dibawah ini :

    ![](C:\Users\Catharina Prisca\Downloads\1\2021-11-17_5.png)

  

  

  - install ssh 

    ![](C:\Users\Catharina Prisca\Downloads\1\2021-11-17_5_1.png)

    

    ```markdown
    PermitRootLogin yes
    RSAAuthentication yes
    service sshd restart
    
    ```

    ![](C:\Users\Catharina Prisca\Downloads\1\2021-11-17_5_2.png)

    

  - cek ssh apakah sudah berjalan atau belum

    ![](C:\Users\Catharina Prisca\Downloads\1\2021-11-17_5_4.png)





2. 

   - Cek lxc dengan menggunakan 

   ```markdown
    lxc-ls -f
   ```

   * Hapus ubuntu landing dengan menggunakan  command seperti dibawah ini, dan buat ubuntu_php7.4 baru dengan menggunakan command lxc-create

   ```markdown
    lxc-destroy ubuntu_php7.4
   ```

   ![](C:\Users\Catharina Prisca\Downloads\2\2021-11-17_6.png)

   ![](C:\Users\Catharina Prisca\Downloads\2\2021-11-17_7.png)

   

   - Setelah membuat baru, gunakan command lxc-start untuk memulai ubuntu_7.4 dan gunakan command lxc-attach untuk membuka ubuntu_7.4. Lalu gunakan install nano untuk mengedit config.

     ![](C:\Users\Catharina Prisca\Downloads\2\2021-11-17_8.png)

   - Atur IP ubuntu_php7.4

     ![](C:\Users\Catharina Prisca\Downloads\2\2021-11-17_9.png)

     Dengan Menggunakan

     ```markdown
     sudo lxc-start -n ubuntu_php7.4
     sudo lxc-attach  -n ubuntu_php7.4
     nano /etc/netplan/10-lxc.yaml
     netplan apply
     
     ```

     ![](C:\Users\Catharina Prisca\Downloads\2\2021-11-17_10.png)

   - Hentikan ubuntu_php7.4 dengan menggunakan command

     ```markdown
     lxc-stop ubuntu_php7.4
     ```

     ![](C:\Users\Catharina Prisca\Downloads\2\2021-11-17_11.png)

   

   - Cek lxc dengan menggunakan 

   ```markdown
    lxc-ls -f
   ```

   ​		![](C:\Users\Catharina Prisca\Downloads\2\2021-11-17_12.png)

   

   - install ssh

     ![](C:\Users\Catharina Prisca\Downloads\2\2021-11-17_13.png)

   - Atur password baru

   ![](C:\Users\Catharina Prisca\Downloads\2\2021-11-17_14.png)

   - cek ssh apakah sudah berjalan atau belum

     ![](C:\Users\Catharina Prisca\Downloads\2\2021-11-17_15.png)






3. vm.local/

- Langkah pertama yang harus dilakukan yakni menginstall laravel  menggunakan ansible. Setelah menginstall, masuk ke ansible tersebut dan buatlah folder laravel

  ![](C:\Users\Catharina Prisca\Downloads\no 3\2021-11-30_2.png)

- Selanjutnya, buat host untuk lxc yang nanti akan di otomasi

  ![](C:\Users\Catharina Prisca\Downloads\no 3\2021-11-30_3.png)

   

  ```markdown
  ubuntu_landing ansible_host=lxc_landing.dev ansible_ssh_user=root ansible_become_pass=123zse456
  
  ```

  * Buatlah directory serta apapun yang akan digunakan untuk menjalankan folder php dan lakukan instalasi

    ![](C:\Users\Catharina Prisca\Downloads\no 3\2021-11-30_3_1.png)

  - ![](C:\Users\Catharina Prisca\Downloads\no 3\2021-11-30_6.png)

    

  - Jika instalasi telah selesai dilakukan, buat folder installcomposer.yml

    ![](C:\Users\Catharina Prisca\Downloads\no 3\2021-11-30_5.png)

    

  - Lakukan instalasi kembali

    ![](C:\Users\Catharina Prisca\Downloads\no 3\2021-11-30_6.png)

    

  - Buatlah folder config.yml

    ![](C:\Users\Catharina Prisca\Downloads\no 3\2021-11-30_7.png)

    

  - Lakukan instalasi

    ![](C:\Users\Catharina Prisca\Downloads\no 3\2021-11-30_8.png)

  - Setting lxc_landing.dev

    ![](C:\Users\Catharina Prisca\Downloads\no 3\2021-11-30_6_1.png)

  - Cek dengan cara membuka vm.local. Jika sukses, maka tampilannya akan seperti berikut ini :

    ![](C:\Users\Catharina Prisca\Downloads\no 3\2021-11-30_9.png)



4. vm.local/blog

   - Seperti pada nomor sebelumnya, langkah pertama dimulai dengan masuk pada folder ansible

     ![](D:\Kuliah\Administrasi Server\no 4\2021-12-01.png)

     

   - Buat host untuk lxc yang nanti akan di otomasi

     ![](D:\Kuliah\Administrasi Server\no 4\2021-12-01_1.png)

   

   -  Buat direktori untuk tasks,templates dan handlers di folder wordpress. Lalu, masuk ke dalam folder tasks untuk menginstall paket

   ![](D:\Kuliah\Administrasi Server\no 4\2021-12-01_2.png)

   

   - ​		Kemudian, masuk ke dalam templates wp.conf yang merupakan tempat configuration pada wordpress ![](D:\Kuliah\Administrasi Server\no 4\2021-12-01_2_1.png)

     

   - Masuk ke dalam templates wordpress.conf

     ![](D:\Kuliah\Administrasi Server\no 4\2021-12-01_3.png)

     

     -  Jalankan ansible kembali untuk menginstall

     ![](D:\Kuliah\Administrasi Server\no 4\2021-12-01_4.png)

     

   - Buka vm.local/blog/ untuk melakukan checking apakah wordpressnya sudah dapat dijalankan atau belum. Jika sudah dapat dijalankan, maka tampilannya akan berubah menjadi berikut :

     ![](D:\Kuliah\Administrasi Server\no 4\2021-12-01_5.png)

     ![](D:\Kuliah\Administrasi Server\no 4\2021-12-01_6.png)

     ![](D:\Kuliah\Administrasi Server\no 4\2021-12-01_7.png)

     ![](D:\Kuliah\Administrasi Server\no 4\2021-12-01_8.png)

