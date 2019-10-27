# PicoCTF2019 Writeup

### Challenge: 
>Can you break into this super secure portal? https://2019shell1.picoctf.com/problem/21888/ (link) or http://2019shell1.picoctf.com:21888

### Hints:
>Never trust the client

- **Passos:**
	Like the last one, you need to look the source code `ctrl+U`
  ```
    <script type="text/javascript">
    function verify() {
      checkpass = document.getElementById("pass").value;
      split = 4;
      if (checkpass.substring(0, split) == 'pico') {
        if (checkpass.substring(split*6, split*7) == '6a8e') {
          if (checkpass.substring(split, split*2) == 'CTF{') {
           if (checkpass.substring(split*4, split*5) == 'ts_p') {
            if (checkpass.substring(split*3, split*4) == 'lien') {
              if (checkpass.substring(split*5, split*6) == 'lz_5') {
                if (checkpass.substring(split*2, split*3) == 'no_c') {
                  if (checkpass.substring(split*7, split*8) == 'b}') {
                    alert("Password Verified")
                    }
                  }
                }

              }
            }
          }
        }
      }
      else {
        alert("Incorrect password");
      }

    }
  </script>
```
  The verify fuction use parts of the flag to verify the password, then you get the positions of the words,
  like `split*6` it's the position 24 of the flag word and the `split*7` it's the 28. So then you just need
  put it together on the right order.


#### Flag: **picoCTF{no_clients_plz_56a8eb}**

