---
title: "Inuiyeji cluster"
date: 2021-04-29T00:07:30+09:00
draft: false
hero: images/inuiyeji-hero.png
menu:
  sidebar:
    name: Inuiyeji
    identifier: school-inuiyeji
    parent: school
    weight: 10
---

# What is Inuiyeji cluster?

'Inuiyeji' cluster is a server cluster that is available for SKKU students who major in Software Engineering. Currently the 'In' server is runs independently, and the 'uiyeji' server is bounded with nfs.

Translation of the below notice about the server. ([https://cs.skku.edu/news/notice/view/2587](https://cs.skku.edu/news/notice/view/2587))

<details>
<summary>Translated Notice</summary>
[Software college's 4-node Linux cluster server setup completed]

4-node Linux cluster server is now available for SW college students.

Students who want to use it can use it freely.

**Hosts:**

```
- swin.skku.edu

- swui.skku.edu

- swye.skku.edu

- swji.skku.edu
```

- SSH Port: 1398 (SKKU's date of establishment)

- ID: Student ID

- Password: Last Name in full capital letters.

```
ex: PARK (If this throws an error, try writing your full name in capital letters, with no spaces)
```

- Others:

1. All accounts are shared by four nodes by NIS.
2. To Change password after login, use the following command: `yppasswd`
3. You can make private homepages by creating a `public_html` directory under the home directory, but due to security concerns, it will be only accessible on campus network. (It is recommended to use this only for html-related classes/courses.)
4. Account related inquiry

- Professor Nam Bum-seok(bnam@skku.edu)
</details>

## Hosts

- 인(In): `swin.skku.edu`
- 의(Ui): `swui.skku.edu`
- 예(Ye): `swye.skku.edu`
- 지(Ji): `swji.skku.edu`

## Connection guide

| Type |   Value    | Remarks                                                                                                        |
| :--: | :--------: | -------------------------------------------------------------------------------------------------------------- |
| Port |    1398    | SKKU's date of establishment                                                                                   |
|  ID  | Student ID | 10 digit                                                                                                       |
|  PW  | Last Name  | All in capital letters; If this throws an error, try writing your full name in capital letters, with no spaces |

# FAQ

### Inuiyeji Cluster

1. Please note that the server is divided by 'In' and 'uiyeji'.

2. Is the server down?
   - We'll provide a server status service soon.

3. I can't connect to the server.
   - This depends on the error.
     - `Connection reset by peer`: This is probably the server blocking your IP. Try accessing from a different IP.
     - It says my password is different: If you've ever connected to 'Inuiyeji' server before, try inserting your password and your last 8 digits of your student ID.
     - If the above solution doesn't work: If you haven't logged in for a long time, your account may not have been created. You can contact Professor Nam Bum-suk and ask him to create an account for you. (Email address: [bnam@skku.edu](mailto:bnam@skku.edu))

4. How can I send/receive a file to/from 'Inuiyeji'?

   - You can use `scp` command-line utility.

   ```sh
   scp -P 1398 (file you want to send) (your ID)@swji.skku.edu:/home/(your ID)/(Directory you want the file sent to)
   scp -P 1398 (자기ID)@swji.skku.edu:(파일 경로/파일명) (파일 다운로드 경로)
   ```

   - You can use sftp programs if you don't want to use the command line. You can use `mobaxterm` for windows.

   [Mobaxterm 사용법](https://skkuoverflow.com/posts/mobaxterm/)

5. I would like to change my password.
   - You can use 'yppasswd' command to change password.

6. I can't copy the file. Is it because of permission problem?
   -  It generally happend when copying course assignment files.
   -  Firse, use command `cp /home/(Course ID)/(directory that your file is located)/* ~/`. If error is not occured, the you can copy the files. Check `cd` or `cd ~` to check if the file is properly copied.
   -  If error occures, you may cope with errors depends on which errors you got.