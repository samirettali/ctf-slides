# Capture The Flag

## CTF

---

# What are CTFs?

---

# Reasons to play

- Learn more about computer security
- You like to solve puzzles
- Improve your problem solving skills
- Have fun

---

# Categories

- Web
- Cryptography
- Steganography
- Forensics
- Binary exploitation

---

# Where to play

- [HackTheBox](https://www.hackthebox.eu/)
- [TryHackMe](https://tryhackme.com/)
- [PortSwigger](https://portswigger.net/web-security)
- [Pentester Lab](https://pentesterlab.com/)

---

# Cryptography

---

# Cryptography

## Brute force attack

We know the algorithm and we try to decrypt the text using a list of keys

---

## Caesar cipher

```
wklv lv d vhfuhw
```

---

## Caesar cipher bruteforce

```
1	vjku ku c ugetgv
2	uijt jt b tfdsfu
3	this is a secret
4	sghr hr z rdbqds
5	rfgq gq y qcapcr
6	qefp fp x pbzobq
7	pdeo eo w oaynap
8	ocdn dn v nzxmzo
9	nbcm cm u mywlyn
10	mabl bl t lxvkxm
11	lzak ak s kwujwl
12	kyzj zj r jvtivk
13	jxyi yi q iushuj
14	iwxh xh p htrgti
15	hvwg wg o gsqfsh
16	guvf vf n frperg
17	ftue ue m eqodqf
18	estd td l dpncpe
19	drsc sc k combod
20	cqrb rb j bnlanc
21	bpqa qa i amkzmb
22	aopz pz h zljyla
23	znoy oy g ykixkz
24	ymnx nx f xjhwjy
25	xlmw mw e wigvix
```

---

# Cryptography

## Frequency analysis

![height:400px](freq.jpg)

---

# Cryptography

## Frequency analysis

```
Cxu oapp wkikh sawt xun oyqn ab
ohannkw aw nyab nkmn lkrqubk A'j
bury q dxxt rhcfnxdhqfykh, nykhk
qhk lappaxwb xs lappaxwb xs ekcb,
cxu oapp wkikh sawt xun nyk rxhhkrn xwk.
```

https://www.boxentriq.com/code-breaking/cryptogram

---

# Cryptography

## Advanced attacks

- Chosen plaintext attack
- Chosen ciphertext attack
- Differential cryptanalysis
- Side channel attacks
- Oracle attacks
- Implementation attacks

---

# Steganography

---

# Steganography

Steganography is the practice of hiding messages.

- It's a very old practice
- Today it's mainly done using images or audio files
- We can use the Least Significant Bit (LSB) of a media file to hide data
- The difference will be unnoticeable

---

# Forensics

---

# Forensics

- Recovering data from a corrupted file system
- Inspecting a memory dump
- Inspecting a network capture
- Analyzing an infected machine

---

# Binary exploitation

---

# Binary exploitation

Memory corruption bugs:

- Buffer overflow
- Heap overflow
- Use after free
- Format string

---

# Binary exploitation

Required knowledge:

- Operating systems
- CPU architecture
- Memory architecture

---

# Web

---

# Web

## SQL Injection

```javascript
const { username, password } = req.body;
const query = `SELECT * FROM users WHERE username = '${username}' AND password = '${password}'`;
const user = doQuery(query);
```

What happens if you enter `admin` as user and `' OR '1'='1` as password?

---

# Web

## SQL Injection

```
SELECT * FROM users WHERE username = 'admin' AND password = '' OR '1'='1'
```

---

# Web

## Arbitrary file read

Let's say we have an application that renders pages using a parameter:

```php
<?php
    $page = $_GET['page'];
    include("/var/www/html/" . $page);
?>
```

What happens if the user enters `../../../../../../../../etc/passwd` as the page?

---

# Web

## Command injection

Let's say we have an application that tells you if a web site is up or not:

```php
<?php
  $url = $_POST["url"];
  system('curl ' . $url, $return_value)
  if ($return_value == 0)
    echo "The website is up"
  else
    echo "The website is down"
?>
```

What happens if the user enters `https://google.com; rm -rf /` as the URL?

---

# Web

## Access control

`/api/customer?id=123`

```javascript
const token = req.headers["token"];
if (!isValid(token)) {
  res.send({ error: "You have an invalid token" });
} else {
  const { id } = req.query;
  const customerInfo = getCustomerInfo(id);
  res.send(id);
}
```

---

# Web

## Server Side Request Forgery

Let's say we have an application that makes screenshots of a website and returns an image using a headless browser:

```typescript
const { url } = req.body;
const browser = openBrowser(url);
const image = browser.screenshot();
res.send({ image });
```

What happens if the user enters a private IP address?

---

# Resources

- [Awesome CTF](https://github.com/apsdehal/awesome-ctf)
- [LiveOverflow](https://www.youtube.com/channel/UClcE-kVhqyiHCcjYwcpfj9w)
- [John Hammond](https://www.youtube.com/channel/UCVeW9qkBjo3zosnqUbG7CFw)
- [My writeups](https://samirettali.com/writeups)

---

# Thanks
