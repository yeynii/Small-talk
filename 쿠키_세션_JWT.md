## ์ฟ ํค(HTTP ์ฟ ํค)

<aside>
๐ช ์ธํฐ๋ท ์ฌ์ฉ์๊ฐ ์ด๋ ํ ์น์ฌ์ดํธ๋ฅผ ๋ฐฉ๋ฌธํ  ๊ฒฝ์ฐ ๊ทธ ์ฌ์ดํธ๊ฐ ์ฌ์ฉํ๊ณ  ์๋ ์๋ฒ๋ฅผ ํตํด ์ธํฐ๋ท ์ฌ์ฉ์์ ์ปดํจํฐ์ ์ค์น๋๋ ์์ ๊ธฐ๋ก ์ ๋ณด ํ์ผ

</aside>

์ ์ฟ ํค์ธ๊ฐ?

- ํจ์ ค๊ณผ ๊ทธ๋ ํ ๋ํ์์ ์์ ์ด ์ง๋์จ ๊ธธ์ ํ์ํ๊ฒ ์ํด ์ฟ ํค์กฐ๊ฐ์ ๋ฐ๋ฅ์ ๋จ์ด๋จ๋ฆฌ๋๊ฒ = ์๋ฒ์ ์์ฒญํ ์ฌ๋์ด ๋๊ตฌ์ธ์ง ํ์ํ๊ธฐ ์ํด ํด๋ผ์ด์ธํธ์ ์ฟ ํค๋ฅผ ๋จ๊ธฐ๋๊ฒ
- ์ ๋์ค ์ด์์ฒด์ ์์ ๋ ํ๋ก๊ทธ๋จ ์ฌ์ด์ ์ ์ก๋๋ ์์ ๋ฐ์ดํฐ ํจํท์ ๋งค์ง ์ฟ ํค๋ผ ๋ถ๋ ๋๋ฐ, ์ด๋ฅผ ์น์์ ์ฐจ์ฉํด์ ์ฌ์ฉํ๊ธฐ ์์ํ ๊ฒ

ํน์ง

- ํด๋ผ์ด์ธํธ์ ์ ์ฅ๋๋ค
- ํ๊ฐ์ 4KB๊น์ง ์ ์ฅ ๊ฐ๋ฅํ๋ค
- ์ด๋ฆ, ๊ฐ, ๋ง๋ฃ๋ ์ง, ๊ฒฝ๋ก ์ ๋ณด๊ฐ ๋ค์ด์๋ค
- ๊ธฐ๋ณธ์ ์ผ๋ก ์น๋ธ๋ผ์ฐ์ ๊ฐ ์ข๋ฃ๋๋ฉด ์ญ์ ๋๊ณ (์ธ์์ฟ ํค), ๋ง๋ฃ๋ ์ง๋ฅผ ์ง์ ํด์ฃผ๋ฉด ๋ง๋ฃ์ผ์ด ๋ผ์ผ ์ญ์ ๋๋ค(์ง์์ฟ ํค)
- ์น ๋ธ๋ผ์ฐ์ ์ ํด๋น ์๋ฒ์ ์ฟ ํค์ ๋ณด๊ฐ ์์ผ๋ฉด HTTP ์์ฒญ์ ๋ฌด์กฐ๊ฑด ๋ด์ ๋ณด๋ธ๋ค
- ํน์  ๋๋ฉ์ธ์์ ์์ฑ๋ ์ฟ ํค๋ ํด๋น ๋๋ฉ์ธ์์๋ง ์ฌ์ฉ๊ฐ๋ฅํ๋ค

## ์ธ์(HTTP ์ธ์)

<aside>
๐ท ํต์ ์ ํ๊ธฐ ์ํด ์๋ก ์ฐ๊ฒฐ๋ ์๊ฐ๋ถํฐ ํต์ ์ ๋ง์น  ๋ ๊น์ง์ ๊ธฐ๊ฐ

ํด๋ผ์ด์ธํธ์ ์น ์๋ฒ๊ฐ์ ํต์  ์ฐ๊ฒฐ์์ ๋ ๊ฐ์ฒด์ ํ์ฑํ๋ ์ ์

์๋ฒ์ ์ธ์์ ๋ณด๋ฅผ ์ ์ฅํด ๋๊ณ  ์ธ์์ฟ ํค๋ฅผ ํด๋ผ์ด์ธํธ์๊ฒ ์ฃผ์ด ์๋ฒ๊ฐ ํด๋ผ์ด์ธํธ๋ฅผ ์๋ณํ  ์ ์๋๋กํ๋ ๋ฐฉ์

์๋ฒ์ ํด๋ผ์ด์ธํธ์ ์ํ ์ ๋ณด๋ฅผ ์ ์ฅํ๋ ๊ธฐ์ 

</aside>

์ ์ธ์์ธ๊ฐ?

- session : ์๊ฐ, ์์ฆ

ํน์ง

- ๋ฐ๋ก ์ฉ๋์ ์ ํ์ด ์๋ค.
- ์๋ฒ์ ์ธ์ ๊ฐ์ฒด๋ฅผ ์์ฑํ๋ฉฐ ๊ฐ ํด๋ผ์ด์ธํธ๋ง๋ค ๊ณ ์ ํ ์ธ์ ID๊ฐ์ ๋ถ์ฌํ๋ค.
- ์ฟ ํค๋ฅผ ์ฌ์ฉํ์ฌ ์ธ์ ID๊ฐ์ ํด๋ผ์ด์ธํธ์ ๋ณด๋ธ๋ค.
- ์น ๋ธ๋ผ์ฐ์ ๊ฐ ์ข๋ฃ๋๋ฉด ์ธ์ ์ฟ ํค๋ ์ญ์ ๋๋ค.

> JWT ํ์
Encoded Header + "." + Encoded Payload + "." + Verify Signature
> 

![แแณแแณแแตแซแแฃแบ 2022-01-21 แแฉแแฅแซ 10.38.38.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2230debd-af83-4f53-b7d7-76246f1b39b7/แแณแแณแแตแซแแฃแบ_2022-01-21_แแฉแแฅแซ_10.38.38.png)

## ์ธ์ฆ๋ฐฉ์

### ์ฟ ํค / ์ธ์ ๋ฐฉ์

[https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Ft1.daumcdn.net%2Fcfile%2Ftistory%2F994BEA345B53368401](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Ft1.daumcdn.net%2Fcfile%2Ftistory%2F994BEA345B53368401)

์์

1. ์ฌ์ฉ์๊ฐ ๋ก๊ทธ์ธ์ ํ๋ค
2. ์๋ฒ์์๋ ๊ณ์ ์ ๋ณด๋ฅผ ์ฝ์ด ์ฌ์ฉ์๋ฅผ ํ์ธํ ํ, ์ฌ์ฉ์์ ๊ณ ์ ํ ID๊ฐ์ ๋ถ์ฌํ์ฌ ์ธ์ ์ ์ฅ์์ ์ ์ฅํ ํ ์ด์ ์ฐ๊ฒฐ๋๋ ์ธ์ID(์ฟ ํค) ๋ฅผ ๋ฐํํ๋ค.
3. ์ฌ์ฉ์๋ ์๋ฒ์์ ํด๋น ์ธ์ID๋ฅผ ๋ฐ์ ์ฟ ํค์ ์ ์ฅ์ ํ ํ, ์ธ์ฆ์ด ํ์ํ ์์ฒญ๋ง๋ค ์ฟ ํค๋ฅผ ํค๋์ ์ค์ด ๋ณด๋ธ๋ค.
4. ์๋ฒ์์๋ ์ฟ ํค๋ฅผ ๋ฐ์ ์ธ์ ์ ์ฅ์์์ ๋์กฐ๋ฅผ ํ ํ ๋์๋๋ ์ ๋ณด๋ฅผ ๊ฐ์ ธ์จ๋ค
5. ์ธ์ฆ์ด ์๋ฃ๋๊ณ  ์๋ฒ๋ ์ฌ์ฉ์์ ๋ง๋ ๋ฐ์ดํฐ๋ฅผ ๋ณด๋ด์ค๋ค.

- ์ฅ์ 
    1. ์ฟ ํค๋ ์ธ์ ์ ์ฅ์์ ๋ด๊ธด ์ ๋ณด๋ฅผ ๊ฐ์ ธ์ค๊ธฐ ์ํ ์ด์ ์ญํ ์ผ ๋ฟ, ์ ์๋ฏธํ ๊ฐ์ ๊ฐ์ง๊ณ  ์์ง๋ ์์ (์ค์ ์ ๋ณด๋ ์๋ฒ ์ธ์ ์ ์ฅ์์)
    2. ์ฌ์ฉ์๋ง๋ค ๊ณ ์  ID ๊ฐ์ ๋ฐ๊ธ๋ฐ์ผ๋ฏ๋ก ์๋ฒ์ธก์์ ์ฟ ํค๊ฐ์ ๋ฐ์์ ๋ ์ผ์ผ์ด ๋ชจ๋  ํ์์ ๋ณด๋ฅผ ํ์ธํ  ํ์ ์์ด ๋ฐ๋ก ํ์์ ๋ณด์ ์ ๊ทผ ํ  ์ ์์

- ๋จ์ 
    1. ํน์  ์ฌ์ฉ์์ HTTP์์ฒญ์ ํด์ปค๊ฐ ๊ฐ๋ก์ฑ์ ๊ทธ ์์ ์ฟ ํค๋ฅผ ํ์น  ์ ์์. ๊ทธ ํ์น ์ฟ ํค๋ฅผ ์ด์ฉํด HTTP ์์ฒญ์ ๋ณด๋ด๋ฉด ์ธ์ ์ ์ฅ์์์ ์ ๋ณด๋ฅผ ์๋ชป ๋ฟ๋ ค์ฃผ๊ฒ ๋จ (์ธ์ ํ์ด์ฌํน ๊ณต๊ฒฉ)
    2. ์๋ฒ์์ ์ธ์ ์ ์ฅ์๋ฅผ ์ฌ์ฉํ๋ฏ๋ก ์ถ๊ฐ์ ์ธ ์ ์ฅ๊ณต๊ฐ์ด ํ์ํ๊ณ  ๋ถํ๋ ๋์์ง (Stateful)
    
    [ํด๊ฒฐ์ฑ]
    
    - ์ฟ ํค/์ธ์ โ HTTPS๋ฅผ ์ฌ์ฉํด ์์ฒญ ์์ฒด๋ฅผ ํ์ทจํด๋ ์์ ์ ๋ณด๋ฅผ ์ฝ๊ธฐ ํ๋ค๊ฒ ํ๋ค.
    - ์ธ์์ ์ ํจ์๊ฐ์ ๋ฃ์ด์ค๋ค.

### JWT (ํ ํฐ ๊ธฐ๋ฐ ์ธ์ฆ ๋ฐฉ์)

<aside>
๐ช Json Web Token์ ์ฝ์. ์ธ์ฆ์ ํ์ํ ์ ๋ณด๋ค์ ์ํธํ ์ํจ ํ ํฐ

</aside>

[https://t1.daumcdn.net/cfile/tistory/995EC2345B53368912](https://t1.daumcdn.net/cfile/tistory/995EC2345B53368912)

์์

1. ์ฌ์ฉ์๊ฐ ๋ก๊ทธ์ธ์ ํ๋ค.

2. ์๋ฒ์์๋ ๊ณ์ ์ ๋ณด๋ฅผ ์ฝ์ด ์ฌ์ฉ์๋ฅผ ํ์ธ ํ, ์ฌ์ฉ์์ ๊ณ ์ ํ ID๊ฐ์ ๋ถ์ฌํ ํ, ๊ธฐํ ์ ๋ณด์ ํจ๊ป Payload์ ๋ฃ์ต๋๋ค.

3. JWT ํ ํฐ์ ์ ํจ๊ธฐ๊ฐ์ ์ค์ ํฉ๋๋ค.

4. ์ํธํํ  SECRET KEY๋ฅผ ์ด์ฉํด ACCESS TOKEN์ ๋ฐ๊ธํฉ๋๋ค.

5. ์ฌ์ฉ์๋ Access Token์ ๋ฐ์ ์ ์ฅํ ํ, ์ธ์ฆ์ด ํ์ํ ์์ฒญ๋ง๋ค ํ ํฐ์ ํค๋์ ์ค์ด ๋ณด๋๋๋ค.

6. ์๋ฒ์์๋ ํด๋น ํ ํฐ์ Verify Signature๋ฅผ SECRET KEY๋ก ๋ณตํธํํ ํ, ์กฐ์ ์ฌ๋ถ, ์ ํจ๊ธฐ๊ฐ์ ํ์ธํฉ๋๋ค.

7. ๊ฒ์ฆ์ด ์๋ฃ๋๋ค๋ฉด, Payload๋ฅผ ๋์ฝ๋ฉํ์ฌ ์ฌ์ฉ์์ ID์ ๋ง๋ ๋ฐ์ดํฐ๋ฅผ ๊ฐ์ ธ์ต๋๋ค.

- (Refresh Token)
    
    8. ์๊ฐ์ด ์ง๋ Access Token์ด ๋ง๋ฃ๋๋ค๊ณ  ๋ณด๊ฒ ์ต๋๋ค.
    
    9. ์ฌ์ฉ์๋ ์ด์ ๊ณผ ๋์ผํ๊ฒ Access Token์ ํค๋์ ์ค์ด ์์ฒญ์ ๋ณด๋๋๋ค.
    
    10~11. ์๋ฒ๋ Access Token์ด ๋ง๋ฃ๋จ์ ํ์ธํ๊ณ  ๊ถํ์์์ ์ ํธ๋ก ๋ณด๋๋๋ค.
    
    - * Access Token ๋ง๋ฃ๊ฐย ๋  ๋๋ง๋ค ๊ณ์ย ๊ณผ์  9~11์ ๊ฑฐ์น  ํ์๋ ์์ต๋๋ค.
    
    ์ฌ์ฉ์(ํ๋ก ํธ์๋)์์ Access Token์ Payload๋ฅผ ํตํด ์ ํจ๊ธฐ๊ฐ์ ์ ์ ์์ต๋๋ค. ๋ฐ๋ผ์ ํ๋ก ํธ์๋ ๋จ์์ API ์์ฒญ ์ ์ ํ ํฐ์ด ๋ง๋ฃ๋๋ค๋ฉด ๋ฐ๋ก ์ฌ๋ฐ๊ธ ์์ฒญ์ ํ  ์๋ ์์ต๋๋ค.
    
    12. ์ฌ์ฉ์๋ Refresh Token๊ณผ Access Token์ ํจ๊ป ์๋ฒ๋ก ๋ณด๋๋๋ค.
    
    **13. ์๋ฒ๋ ๋ฐ์ Access Token์ด ์กฐ์๋์ง ์์๋์ง ํ์ธํํ, Refresh Token๊ณผ ์ฌ์ฉ์์ DB์ ์ ์ฅ๋์ด ์๋ Refresh Token์ ๋น๊ตํฉ๋๋ค. Token์ด ๋์ผํ๊ณ  ์ ํจ๊ธฐ๊ฐ๋ ์ง๋์ง ์์๋ค๋ฉด ์๋ก์ด Access Token์ ๋ฐ๊ธํด์ค๋๋ค.**
    
    14. ์๋ฒ๋ ์๋ก์ด Access Token์ ํค๋์ ์ค์ด ๋ค์ API ์์ฒญ์ ์งํํฉ๋๋ค.
    

- ์ฅ์ 
    1. ๋ณ๋์ ์ ์ฅ์ ๊ด๋ฆฌ๊ฐ ํ์์๋ค (Stateless)
    2. ํ์ฅ์ฑ์ด ๋ฐ์ด๋๊ณ  ์ ์ง, ๋ณด์ํ๋๋ฐ ์ ๋ฆฌํจ
    3. ํ ํฐ ๊ธฐ๋ฐ์ผ๋ก ํ๋ ๋ค๋ฅธ ์ธ์ฆ ์์คํ์ ์ ๊ทผ์ด ๊ฐ๋ฅ ํจ. (ex. ํ์ด์ค๋ถ ๋ก๊ทธ์ธ, ๊ตฌ๊ธ ๋ก๊ทธ์ธ ๋ฑ)

- ๋จ์ 
    1. ์ด๋ฏธ ๋ฐ๊ธ๋ jwt์ ๋ํด์ ๋์ดํฌ ์ ์์. ์ธ์/์ฟ ํค๋ฐฉ์์ ์์์ ์ธ ์ ๊ทผ์ด ์์๋๋ ID์ ํด๋น์ธ์์ ์ง์๋ฒ๋ฆฌ๋ฉด ์ธ์ฆ์ด ๋ง๋ฃ๋์ง๋ง jwt๋ฐฉ์์ ๋ถ๊ฐ๋ฅ
    2. payload ์ ๋ณด๊ฐ ์ ํ์ . payload๋ ์ํธํ ๋์ง ์๊ธฐ ๋๋ฌธ์ ์ค์ ์ ๋ณด๋ ๋ฃ์ ์ ์์
    3. JWT์ ๊ธธ์ด๋ ์ธ์/์ฟ ํค์ ๋นํด ๊ธธ๋ค. ์์ฒญ์ด ๋ง์์ง์๋ก ์๋ฒ์ ์์๋ญ๋น๊ฐ ๋ฐ์
    
    [ํด๊ฒฐ์ฑ]
    
    - Access Token(์ ํจ๊ธฐ๊ฐ ์งง์)๊ณผ Refresh Token(์ ํจ๊ธฐ๊ฐ ๊ธบ)์ ํจ๊ป ๋ฐ๊ธ
        
        โ Refresh Token์ ์ ์ฅ์์ ๋ํ ๊ณ ๋ฏผ... ์ฃผ๋ก Access Token์ local storage์ Refresh Token์ ์๋ฒ์ฌ์ด๋์ ์ ์ฅ (-> ์ข ๋ ์์๋ณผ ๊ฒ)
        
        โ ํ๋ก ํธ, ์๋ฒ ๋ชจ๋ ๊ตฌํ์ด ๋ณต์กํด์ง
        
        โ Access Token์ด ๋ง๋ฃ ๋  ๋๋ง๋ค ์๋กญ๊ฒ ๋ฐ๊ธํ๋ ๊ณผ์ ์์ ์๊ธฐ๋ HTTP ์์ฒญ ํ์๊ฐ ๋ง์ ์๋ฒ์ ์์๋ญ๋น๊ฐ ๋ฐ์ - ํ๋ก ํธ๋จ์์ Access Token payload๋ฅผ ํตํด ์ ํจ๊ธฐ๊ฐ์ ์์๋ด์ด ๊ณผ์ ์ ๋จ์ถํ  ์ ์์
