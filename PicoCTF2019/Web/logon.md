# CPBSB3-CTF Writeup

### Challenge: 
>The factory is hiding things from all of its users. Can you login as logon and find what they've been looking at? https://2019shell1.picoctf.com/problem/37907/ (link) or http://2019shell1.picoctf.com:37907

### Hint:
> Hmm it doesn't seem to check anyone's password, except for {{name}}'s?

- **Passos:**
	This chall has something to do with the cookies site. First you will need of some extension to edit the cookies, i am using the 
  `Cookie Quick Manager`
  
  ![cookie quick manager](https://github.com/trolliama/ctf-writeups/blob/master/PicoCTF2019/Web/images/2019-10-27_00-04.png)

	Now with the extension installed you can modify the cookie `admin:False` to True, and then get the flag.
  ![cookie quick manager](https://github.com/trolliama/ctf-writeups/blob/master/PicoCTF2019/Web/images/2019-10-27_00-04_1.png)


#### Flag: **picoCTF{th3_c0nsp1r4cy_l1v3s_2e19dad3}**

