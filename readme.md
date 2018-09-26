# Cara Menggunakan SSH Key untuk koneksi ke Github

Referensi jika ingin googling dengan kata kunci **github ssh key**.

## Mengapa menggunakan SSH?

* Alasan Keamanan repository anda.
* Tidak repot menuliskan username dan password setiap kali **Push & Pull**.
* Lebih cepat akses ke remote server.
* Cara kerjanya adalah Github mengidentifikasi laptop anda dengan key number.

## Cara Generate SSH baru di laptop anda.

Jika tidak yakin apakah anda sudah memeliki SSH Key dilaptop? 

Cara cek SSH di laptop anda, ketik dibawah ini:

	cat ~/.ssh/id_rsa.pub
	
Apabila muncul kode seperti ini : 

	ssh-rsa AAAAB3Nza..xxxxxxxxxxxxxxxxxxxyyyyyyyyyyyyyyyyyyyyyyyyyyzzzzzzzzzzzzzzzzzzzxxxxxxxxxxxxxxxxxxxxxxxyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzxxxxxxxxxxxxxxxxxxxxxxxxxxyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyzzzzzzzzzzzzz dyo-medio@dyo-mac.local
	
xyz adalah key yang saya samarkan :)

### Apabila tidak muncul baris seperti diatas? 

Anda harus generate key baru, caranya:

	ssh-keygen -t rsa -b 4096 -C "email_anda@contoh.com"
	
Kemudian muncul pertanyaan, anda enter-enter saja untuk set secara default.

### Apabila muncul baris seperti diatas?

Anda harus menambahkan key tsb ke SSH-Agent, cara nya:

	eval $(ssh-agent -s)
	--> akan muncul: Agent pid xxxxx
	
Tambahkan key ke ssh-agent:

	ssh-add -K ~/.ssh/id_rsa
	
Kemudian tambahkan SSH key ke account Github anda.

Sebelumnya copy dulu key anda ke clipboard, dengan cara:

	pbcopy < ~/.ssh/id_rsa.pub
	
Anda login ke account github.com, dengan langkah:

1. Ke profile anda.
2. Klik Setting.
3. Klik ssh key.
4. Beri nama pada form.
5. Paste key ke dalam kotak yang disediakan.
	
Pelajari Git lebih lanjut:

[https://git-scm.com/book/id/v1/Memulai-Git-Dasar-Git](https://git-scm.com/book/id/v1/Memulai-Git-Dasar-Git)

---


	