<p align="center">
    <img src="https://github.com/user-attachments/assets/cec56db6-eecb-44ea-9cab-1c7f8ed59575"
        height="280">
</p>
<p align="center">
<a href="https://github.com/irtsa-dev/grsa/releases/tag/v1.0.0">
        <img src="https://img.shields.io/badge/release-1.0.0-brightgreen"
            alt="release"></a>
<a href="https://github.com/irtsa-dev/grsa/issues">
        <img src="https://custom-icon-badges.demolab.com/github/issues-raw/irtsa-dev/grsa?logo=issue"
            alt="issues"></a>
<a href="https://github.com/irtsa-dev/grsa/pulls">
        <img src="https://custom-icon-badges.demolab.com/github/issues-pr/irtsa-dev/grsa?logo=git-pull-request"
            alt="pulls"></a>
</p>
<p align="center">
<br />
<b>GRSA</b> is a simple implementation of <b><a href="https://en.wikipedia.org/wiki/RSA_(cryptosystem)">RSA</a> Key Generation</b> in <a href="https://codedocs.ghtools.xyz">greyscript</a> for the game <a href="https://store.steampowered.com/app/605230/Grey_Hack">Grey Hack</a>. Comes with included encryption and decryption functions.
</p>
<br />
<br />
<h2 align="center">Installation</h2>
<p align="center">
To install, first copy the code of <b>grsa.src</b> file found <a href="https://github.com/irtsa-dev/grsa/blob/main/grsa/grsa.src">here</a> and paste it into an open <b>Code Editor</b> process in-game. Afterwards, you must save this to <code>/bin</code> as <code>grsa</code> <i>(or optionally any path and name you will later rememeber)</i> making sure to enable <b>Allow import</b>. Once you have done this, you may not utilize <code>import_code("/bin/grsa")</code> or if you hadn't saved it as recommended then <code>import_code("(path-to-file)"</code> at the top of any file that you wish to use <b>GRSA</b> in.
</p>
<br />
<p align="center">
Optionally, you can simply copy the code of <b>grsa.src</b> file found <a href="https://github.com/irtsa-dev/grsa/blob/main/grsa/grsa.src">here</a> and paste it at the top of any file you wish to use <b>GRSA</b> in.
</p>
<br />
<br />
<br />
<br />
<br />
<h2 align="center">Usage</h2>
<p align="center">
Primary usage utilizes <b>three</b> functions in the <code>grsa.src</code> file with <b>two</b> additional functions for secondary usage.
</p>
<br />
<p align="center">
The first function you must utilize is the <code>genKeyPair()</code> function which takes an argument <code>primeLength</code> which dictates how many digits long the prime numbers <code>p</code> and <code>q</code> are. This function will return a type <b>List</b> where the first element is the <code>publickey</code> and the second element is the <code>privatekey</code>. Do note that the larger the <code>primeLength</code> value, the longer it will take to generate the <b>keys</b>.
</p>
<br />
<p align="center">
Afterwards, you will primarily utilize <code>fullencrypt()</code> and <code>fulldecrypt()</code> functions. The encryption function takes in the arguments of <code>text</code> and <code>publickey</code> and will return the given text encrypted using the publickey. The decryption function takes in the arguments of <code>text</code> and <code>privatekey</code> and will return the given text decrypted using the privatekey.
</p>
<br />
<p align="center">
Optionally, if you do not want the characters of the encrypted text to be returned, you can utilize the <code>encrypt()</code> function which takes the same arguments of the <code>fullencrypt()</code> function but will return the unicode representations of the encrypted text instead of the characters. You can also optionally utilize the <code>decrypt()</code> function which takes the list of unicode numbers from the <code>encrypt()</code> function instead as an argument (<code>nums</code>) along with the <code>privatekey</code> and will return the decrypted text.
</p>
<br />
<br />
<p align="center">
Below are examples of the functions in use:
</p>

```js
Keys = genKeyPair(4)
puk = Keys[0]
pik = Keys[1]


text = "This is sample text."
encryptedText = fullencrypt(text, puk)
print(encryptedText) // Will print off the encrypted text.

decryptedText = fulldecrypt(encryptedText, pik)
print(decryptedText) // Will print off the decrypted text which should be the same as the original text.
```
```js
Keys = genKeyPair(4)
puk = Keys[0]
pik = Keys[1]


text = "This is sample text."
encryptedText = encrypt(text, puk)
print(encryptedText) // Will print off the unicode values of the encrypted text

decryptedText = decrypt(encryptedText, pik)
print(decryptedText) // Will print off the decrypted text which should be the same as the original text.
```
<br />
<br />
<br />
<br />
<br />
<br />
<h2 align="center">Additional Notes</h2>
<p align="center">
Note that functions may be added, removed, changed, or even renamed in future updates. Functions may also have their functionality changed in future updates by request or if it seems to work better another way. You may utilize the <a href="https://github.com/irtsa-dev/grsa/discussions">Discussions</a> tab to request changes or additions and the <a href="https://github.com/irtsa-dev/grsa/issues">Issues</a> tab to report issues/bugs you find.
