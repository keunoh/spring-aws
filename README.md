AWS deployment ๐ฒ
- ์ถ์ฒ : ์คํ๋ง ๋ถํธ์ AWS๋ก ํผ์ ๊ตฌํํ๋ ์น ์๋น์ค(์ด๋์ฑ ์ง์)
---

1. TDD์ ๋จ์ํ์คํธ๋ ๋ค๋ฅด๋ค.  
   : TDD๋ ํ์คํธ ๋จผ์  ์์ฑ -> ํ์คํธ ํต๊ณผํ ํ๋ก๋์ ์ฝ๋ ์์ฑ
   -> ํ๋ก๋์ ์ฝ๋ ๋ฆฌํฉํ ๋ง  
   ๋จ์ํ์คํธ๋ TDD์ ์ฒซ ๋ฒ์งธ ๋จ๊ณ์ธ ๊ธฐ๋ฅ ๋จ์์ ํ์คํธ์ฝ๋๋ฅผ ์์ฑ

2. @SpringBootApplication
   : ํ๋ก์ ํธ์ ๋ฉ์ธ ํด๋์ค๋ก์จ ์คํ๋ง ๋ถํธ์ ์๋์ค์ , ์คํ๋ง Bean
   ์ฝ๊ธฐ์ ์์ฑ์ ๋ชจ๋ ์๋์ผ๋ก ์ค์ , @SpringBootApplication์ด ์๋ ์์น๋ถํฐ ์ค์ ์ ์ฝ์ด ๊ฐ๊ธฐ ๋๋ฌธ์ด ์ด ํด๋์ค๋ ํญ์ ํ๋ก์ ํธ์
   ์ต์๋จ์ ์์นํ์ฌ์ผ ํ๋ค.

3. @RunWith(SpringRunner.class)
   : ํ์คํธ๋ฅผ ์งํํ  ๋ JUnit์ ๋ด์ฅ๋ ์คํ์ ์ด์ธ ๋ค๋ฅธ ์คํ์๋ฅผ
   ์คํ์ํจ๋ค. ์ฌ๊ธฐ์๋ SpringRunner๋ผ๋ ์คํ๋ง ์คํ์๋ฅผ ์ฌ์ฉํ๋ค.
   ์ฆ, ์คํ๋ง ๋ถํธ ํ์คํธ์ JUnit ์ฌ์ด์ ์ฐ๊ฒฐ์ ์ญํ 

4. @WebMvcTest
   : ์ฌ๋ฌ ์คํ๋ง ํ์คํธ ์ด๋ธํ์ด์ ์ค, Web(Spring MVC)์ ์ง์คํ  ์์๋ ์ด๋ธํ์ด์์ด๋ค. ์ ์ธํ  ๊ฒฝ์ฐ @Controller, @ControllerAdvice๋ฑ ์ฌ์ฉ์ด ๊ฐ๋ฅํ๋ค. ๋จ, @Service, @Component, @Repository ๋ฑ์ ์ฌ์ฉํ  ์ ์๋ค.

5. @RequiredArgsConstructor
   : ์ ์ธ๋ ๋ชจ๋  final ํ๋๊ฐ ํฌํจ๋ ์์ฑ์๋ฅผ ์์ฑํด ์ค๋ค.
    final์ด ์๋ ํ๋๋ ์์ฑ์์ ํฌํจ๋์ง ์๋๋ค.

6. @Entity
   : ํ์ด๋ธ๊ณผ ๋งํฌ๋  ํด๋์ค์์ ๋ํ๋๋๋ค. ๊ธฐ๋ณธ๊ฐ์ผ๋ก ํด๋์ค์ ์นด๋ฉ
   ์ผ์ด์ค ์ด๋ฆ์ ์ธ๋์ค์ฝ์ด ๋ค์ด๋ฐ์ผ๋ก ํ์ด๋ธ ์ด๋ฆ์ ๋งค์นญํฉ๋๋ค.
   ex) SalesManager.java -> sales_manager table

7. @GeneratedValue
   : PK์ ์์ฑ ๊ท์น์ ๋ํ๋๋๋ค. ์คํ๋ง ๋ถํธ 2.0์์๋ GenerationType.IDENTITY ์ต์์ ์ถ๊ฐํด์ผ๋ง auto_increment๊ฐ ๋ฉ๋๋ค

8. @Column
   : ํ์ด๋ธ์ ์ปฌ๋ผ์ ๋ํ๋ด๋ฉฐ ๊ตณ์ด ์ ์ธํ์ง ์๋๋ผ๋ ํด๋น ํด๋์ค์
   ํ๋๋ ๋ชจ๋ ์ปฌ๋ผ์ด ๋ฉ๋๋ค. ์ฌ์ฉํ๋ ์ด์ ๋, ๊ธฐ๋ณธ๊ฐ ์ธ์ ์ถ๊ฐ๋ก
   ๋ณ๊ฒฝ์ด ํ์ํ ์ต์์ด ์์ผ๋ฉด ์ฌ์ฉํฉ๋๋ค.  
   ex) ๋ฌธ์์ด์ ๊ฒฝ์ฐ VARCHAR(255)๊ฐ ๊ธฐ๋ณธ ๊ฐ์ธ๋ฐ, ์ฌ์ด์ฆ๋ฅผ 500์ผ๋ก
   ๋๋ฆฌ๊ณ  ์ถ๋ค๋๊ฐ, ํ์์ TEXT๋ก ๋ณ๊ฒฝํ๊ณ  ์ถ๋ค๋๊ฐ ๋ฑ๋ฑ.

9. @Transactional
   : ํด๋น ์ ๋ธํ์ด์์ด ๋ถ์ ๋ฉ์๋๋ ๋ฉ์๋๊ฐ ํฌํจํ๊ณ  ์๋ ์์ ์ค์
   ํ๋๋ผ๋ ์คํจํ  ๊ฒฝ์ฐ ์ ์ฒด ์์์ ์ทจ์ํ๋ค.  
   ๊ด๋ จ URL : https://tecoble.techcourse.co.kr/post/2021-05-25-transactional/

10. @MappedSuperclass
    : JPA Entity ํด๋์ค๋ค์ด BaseTimeEntity๋ฅผ ์์ํ  ๊ฒฝ์ฐ ํ๋๋ค
    (createdDate, modifiedDate)๋ ์ปฌ๋ผ์ผ๋ก ์ธ์ํ๋๋ก ํฉ๋๋ค.

11. @EntityListeners(AuditingEntityListener.class)
    : BaseTimeEntity ํด๋์ค์ Auditing ๊ธฐ๋ฅ์ ํฌํจ์ํต๋๋ค.

12. @CreatedDate
    : Entity๊ฐ ์์ฑ๋์ด ์ ์ฅ๋  ๋ ์๊ฐ์ด ์๋ ์ ์ฅ๋ฉ๋๋ค.

13. @LastModifiedDate
    : ์กฐํํ Entity์ ๊ฐ์ ๋ณ๊ฒฝํ  ๋ ์๊ฐ์ด ์๋ ์ ์ฅ๋ฉ๋๋ค.

14. @EnableJpaAuditing
    : JPA Auditing ํ์ฑํ, ์ต์์ ์ ํ๋ฆฌ์ผ์ด์ ํด๋์ค์ ์ถ๊ฐ

15. @Enumerated(EnumType.STRING)
   : JPA๋ก ๋ฐ์ดํฐ๋ฒ ์ด์ค๋ก ์ ์ฅํ  ๋ Enum๊ฐ์ ์ด๋ค ํํ๋ก ์ ์ฅํ ์ง๋ฅผ
   ๊ฒฐ์ ํฉ๋๋ค. ๊ธฐ๋ณธ์ ์ผ๋ก๋ int๋ก ๋ ์ซ์๊ฐ ์ ์ฅ๋ฉ๋๋ค. ์ซ์๋ก ์ ์ฅ๋๋ฉด ๋ฐ์ดํฐ๋ฒ ์ด์ค๋ก ํ์ธํ  ๋ ๊ทธ ๊ฐ์ด ๋ฌด์จ ์ฝ๋๋ฅผ ์๋ฏธํ๋์ง ์ ์๊ฐ ์์ต๋๋ค. ๊ทธ๋์ ๋ฌธ์์ด (EnumType.STRING)์ผ๋ก ์ ์ฅ๋  ์ ์๋๋ก ์ ์ธํฉ๋๋ค.

16. @EnableWebSecurity
   : Spring Security ์ค์ ๋ค์ ํ์ฑํ์์ผ ์ค๋๋ค.
---
# Spring Web Layer
![2022-10-19(spring web layer)](https://user-images.githubusercontent.com/96904103/196657295-4d42733d-c022-43d1-8e72-0b3a6bcd5c89.png)


###Service Layer ์คํด###
	: ๋ง์ ๋ถ๋ค์ด ์คํดํ๊ณ  ๊ณ์  ๊ฒ์ด, Service์์ ๋น์ง๋์ค ๋ก์ง์
	์ฒ๋ฆฌํด์ผ ํ๋ค๋ ๊ฒ์๋๋ค. ํ์ง๋ง ์ ํ ๊ทธ๋ ์ง ์์ต๋๋ค. Service๋
	ํธ๋์ญ์, ๋๋ฉ์ธ ๊ฐ ์์ ๋ณด์ฅ์ ์ญํ ๋ง ํฉ๋๋ค.

1. Web Layer
   - ํํ ์ฌ์ฉํ๋ ์ปจํธ๋กค๋ฌ(@Controller)์ JSP/Freemarker ๋ฑ์ ๋ทฐ ํํ๋ฆฟ ์์ญ์๋๋ค.
   - ์ด์ธ์๋ ํํฐ(@Filter), ์ธํฐ์ํฐ, ์ปจํธ๋กค๋ฌ ์ด๋๋ฐ์ด์ค(@ControllerAdvice) ๋ฑ ์ธ๋ถ
     ์์ฒญ๊ณผ ์๋ต์ ๋ํ ์ ๋ฐ์ ์ธ ์์ญ์ ์ด์ผ๊ธฐํฉ๋๋ค.
2. Service Layer 
   - @Service์ ์ฌ์ฉ๋๋ ์๋น์ค ์์ญ์๋๋ค. 
   - ์ผ๋ฐ์ ์ผ๋ก Cotroller์ Dao์ ์ค๊ฐ ์์ญ์์ ์ฌ์ฉ๋ฉ๋๋ค. 
   - @Transcational์ด ์ฌ์ฉ๋์ด์ผ ํ๋ ์์ญ์ด๊ธฐ๋ ํฉ๋๋ค.
3. Repository Layer
   - Database์ ๊ฐ์ด ๋ฐ์ดํฐ ์ ์ฅ์์ ์ ๊ทผํ๋ ์์ญ์๋๋ค. 
   - Dao(Data Access Object)์์ญ์ผ๋ก ์ดํดํ์๋ฉด ์ฌ์ธ ๊ฒ์๋๋ค.
4. Dtos
   - Dto(Data Transfer Object)๋ ๊ณ์ธต ๊ฐ์ ๋ฐ์ดํฐ ๊ตํ์ ์ํ ๊ฐ์ฒด๋ฅผ ์ด์ผ๊ธฐํ๋ฉฐ Dtos๋ ์ด๋ค์ ์์ญ์ ์ด์ผ๊ธฐํฉ๋๋ค. 
   - ์๋ฅผ ๋ค์ด ๋ทฐ ํํ๋ฆฟ ์์ง์์ ์ฌ์ฉ๋  ๊ฐ์ฒด๋ Repository Layer์์ ๊ฒฐ๊ณผ๋ก ๋๊ฒจ์ค ๊ฐ์ฒด ๋ฑ์ด ์ด๋ค์ ์ด์ผ๊ธฐํฉ๋๋ค.
5. Domain Model
   - ๋๋ฉ์ธ์ด๋ผ ๋ถ๋ฆฌ๋ ๊ฐ๋ฐ ๋์์ ๋ชจ๋  ์ฌ๋์ด ๋์ผํ ๊ด์ ์์ ์ดํดํ  ์ ์๊ณ  ๊ณต์ ํ  ์ ์๋๋ก ๋จ์ํ์ํจ ๊ฒ์ ๋๋ฉ์ธ ๋ชจ๋ธ์ด๋ผ๊ณ  ํฉ๋๋ค. 
   - ์ด๋ฅผํ๋ฉด ํ์ ์ฑ์ด๋ผ๊ณ  ํ๋ฉด ๋ฐฐ์ฐจ, ํ์น, ์๊ธ ๋ฑ์ด ๋ชจ๋ ๋๋ฉ์ธ์ด ๋  ์ ์์ต๋๋ค. @Entity๊ฐ ์ฌ์ฉ๋ ์์ญ ์ญ์ ๋๋ฉ์ธ ๋ชจ๋ธ์ด๋ผ๊ณ  ์ดํดํ๋ฉด ๋ฉ๋๋ค.
   - ๋ค๋ง, ๋ฌด์กฐ๊ฑด ๋ฐ์ดํฐ๋ฒ ์ด์ค์ ํ์ด๋ธ๊ณผ ๊ด๊ณ๊ฐ ์์ด์ผ๋ง ํ๋ ๊ฒ์์๋๋๋ค. 
   - VO์ฒ๋ผ ๊ฐ ๊ฐ์ฒด๋ค๋ ์ด ์์ญ์ ํด๋นํ๊ธฐ ๋๋ฌธ์๋๋ค.

---
# Persistence Context

1. DB ์ฟผ๋ฆฌ๋ฌธ์ด ์์ด๋ ํ์ด๋ธ์ด ์๋ฐ์ดํ ๋จ(@Service๊ตฌ๊ฐ์์)
   @Service ์ ๋ธํ์ด์์ด ๋ถ์ด์๊ธฐ ๋๋ฌธ์ ๋ฐ์ํ๋ ๊ฒ์ ์๋
     : JPA์ ์์์ฑ ์ปจํ์คํธ ๋๋ฌธ์๋๋ค. ์์์ฑ ์ปจํ์คํธ๋, ์ํฐํฐ๋ฅผ
     ์๊ตฌ ์ ์ฅํ๋ ํ๊ฒฝ์๋๋ค. ์ผ์ข์ ๋ผ๋ฆฌ์  ๊ฐ๋์ด๋ผ๊ณ  ๋ณด์๋ฉด ๋๋ฉฐ,
     JPA์ ํต์ฌ ๋ด์ฉ์ ์ํฐํฐ๊ฐ ์์์ฑ ์ปจํ์คํธ์ ํฌํจ๋์ด ์๋ ์๋๋๋ก ๊ฐ๋ฆฝ๋๋ค. JPA์ ์ํฐํฐ ๋งค๋์ (Entity Manager)๊ฐ ํ์ฑํ๋ ์ํ๋ก(Spring Data Jpa๋ฅผ ์ด๋ค๋ฉด ๊ธฐ๋ณธ ์ต์) ํธ๋์ญ์ ์์์ ๋ฐ์ดํฐ๋ฒ ์ด์ค์์ ๋ฐ์ดํฐ๋ฅผ ๊ฐ์ ธ์ค๋ฉด ์ด ๋ฐ์ดํฐ๋ ์์์ฑ ์ปจํ์คํธ๊ฐ ์ ์ง๋ ์ํ์๋๋ค. ์ด ์ํ์์ ํด๋น ๋ฐ์ดํฐ์ ๊ฐ์ ๋ณ๊ฒฝํ๋ฉด ํธ๋์ญ์์ด ๋๋๋ ์์ ์ ํด๋น ํ์ด๋ธ์ ๋ณ๊ฒฝ๋ถ์ ๋ฐ์ํฉ๋๋ค. ์ฆ, Entity ๊ฐ์ฒด์ ๊ฐ๋ง ๋ณ๊ฒฝํ๋ฉด ๋ณ๋๋ก Update ์ฟผ๋ฆฌ๋ฅผ ๋ ๋ฆดํ์๊ฐ ์๋ค๋ ๊ฒ์ด์ฃ . ์ด ๊ฐ๋์ ๋ํฐ ์ฒดํน(Dirty Checking)์ด๋ผ๊ณ  ํฉ๋๋ค.

2. ๋ํฐ ์ฒดํน(Dirty Checking)
   : ๊ด๋ จ URL : https://jojoldu.tistory.com/415

---
# Template Engine

1. ํํ๋ฆฟ ์์ง
   : ์ง์ ๋ ํํ๋ฆฟ ์์๊ณผ ๋ฐ์ดํฐ๊ฐ ํฉ์ณ์ ธ HTML ๋ฌธ์๋ฅผ ์ถ๋ ฅํ๋ ์ํํธ์จ์ด๋ฅผ ์ด์ผ๊ธฐํฉ๋๋ค. JSP, Freemarker๋ ์๋ฒ ํํ๋ฆฟ ์์ง, ๋ฆฌ์กํธ, ๋ทฐ๋ ํด๋ผ์ด์ธํธ ํํ๋ฆฟ ์์ง์ด๋ผ๊ณ  ๋ถ๋ฆฐ๋ค. ์๋ฐ์คํฌ๋ฆฝํธ๋ ๋ธ๋ผ์ฐ์  ์์์ ์๋ํฉ๋๋ค. ์๋ฒ ํํ๋ฆฟ ์์ง์ ์๋ฒ์์ ๊ตฌ๋๋ฉ๋๋ค.

2. ํ์(์ด๋์ฑ)๊ฐ ์๊ฐํ๋ ํํ๋ฆฟ ์์ง๋ค์ ๋จ์ ์ ๋ค์๊ณผ ๊ฐ์ต๋๋ค.
    - Thymeleaf : ์คํ๋ง ์ง์์์ ์ ๊ทน์ ์ผ๋ก ๋ฐ๊ณ  ์์ง๋ง ๋ฌธ๋ฒ์ด ์ด๋ ต์ต๋๋ค. HTML ํ๊ทธ์ ์์ฑ์ผ๋ก ํํ๋ฆฟ ๊ธฐ๋ฅ์ ์ฌ์ฉํ๋ ๋ฐฉ์์ด ๊ธฐ์กด ๊ฐ๋ฐ์๋ถ๋ค๊ป ๋์ ํ๋ค๋ก ๋๊ปด์ง๋ ๊ฒฝ์ฐ๊ฐ ๋ง์ต๋๋ค. ์ค์ ๋ก ์ฌ์ฉํด ๋ณธ ๋ถ๋ค์ ์๋ฐ์คํฌ๋ฆฝํธ ํ๋ ์์ํฌ๋ฅผ ๋ฐฐ์ฐ๋ ๊ธฐ๋ถ์ด๋ผ๊ณ  ํ๊ธฐ๋ฅผ ์ด์ผ๊ธฐํ๊ธฐ๋ ํฉ๋๋ค.

3. mustache(ํํ๋ฆฟ ์์ง) ์ฌ์ฉ์ ์ฅ์ 
   : ๋ฌธ๋ฒ์ด ๋ค๋ฅธ ํํ๋ฆฟ ์์ง๋ณด๋ค ์ฌํํฉ๋๋ค. ๋ก์ง์ฝ๋๋ฅผ ์ฌ์ฉํ  ์ ์์ด View์ ์ญํ ๊ณผ ์๋ฒ์ ์ญํ ์ด ๋ชํํ ๋ถ๋ฆฌ๋ฉ๋๋ค. Mustache.js์ Mustache.java 2๊ฐ์ง๊ฐ ๋ค ์์ด, ํ๋์ ๋ฌธ๋ฒ์ผ๋ก ํด๋ผ์ด์ธํธ/์๋ฒ ํํ๋ฆฟ์ ๋ชจ๋ ์ฌ์ฉํฉ๋๋ค.

4. mustache์ ํด๋ ๊ธฐ๋ณธ ์์น
   : src/main/resources/templates <- ์ด ์์น์ ๋จธ์คํ์น ํ์ผ์ ๋๋ฉด์คํ๋ง ๋ถํธ์์ ์๋์ผ๋ก ๋ก๋ฉํฉ๋๋ค.

5. ํ์ด์ง ๋ก๋ฉ์๋
   : ์๋๋ฅผ ๋์ด๊ธฐ ์ํ์ฌ css๋ header์, js๋ footer ๋๋๊ฒ ์ข๋ค.

6. ๋ธ๋ผ์ฐ์ ์ ์ค์ฝํ
   : ๋ธ๋ผ์ฐ์ ์ ์ค์ฝํ๋ ๊ณต์ฉ ๊ณต๊ฐ์ผ๋ก ์ฐ์ด๊ธฐ ๋๋ฌธ์ ๋์ค์ ๋ก๋ฉ๋ js์ init, save๊ฐ ๋จผ์  ๋ก๋ฉ๋ js์ function์ ๋ฎ์ด์ฐ๊ฒ ๋ฉ๋๋ค. ์ฌ๋ฌ ์ฌ๋์ด ์ฐธ์ฌํ๋ ํ๋ก์ ํธ์์๋ ์ค๋ณต๋ ํจ์์ด๋ฆ์ ์์ฃผ ๋ฐ์ ํ  ์ ์์ต๋๋ค. ๋ชจ๋  function ์ด๋ฆ์ ํ์ธํ๋ฉด์ ๋ง๋ค ์๋ ์์ต๋๋ค. ์ด ๋ฌธ์ ๋ฅผ ํผํ๋ ค๊ณ  index.js๋ง์ ์ ํจ๋ฒ์๋ฅผ ๋ง๋ค์ด์ ์ฌ์ฉํฉ๋๋ค. ์ด๋ ๊ฒ๋๋ฉด index๊ฐ์ฒด ์์์๋ง function์ด ์ ํจํ๊ธฐ ๋๋ฌธ์ ๋ค๋ฅธ js์ ๊ฒน์น  ์ํ์ด ์ฌ๋ผ์ง๋๋ค.

7. ๋ฐ๋๋ผ ์๋ฐ์คํฌ๋ฆฝํธ
   : ํ๋ฌ๊ทธ์ธ์ด๋, ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ ์ฌ์ฉํ์ง ์์ ์์ ์๋ฐ์คํฌ๋ฆฝํธ๋ฅผ ์ด์ผ๊ธฐํฉ๋๋ค. ์ธ๊ตญ์์๋ ๋ฐ๋๋ผ(Vanilla) = ์ผ๋ฐ(Plain)์ ์๋ฏธํจ

8. staticํด๋
   : ์คํ๋ง๋ถํธ๋ ๊ธฐ๋ณธ์ ์ผ๋ก src/main/resources/static์ ์์นํ ์๋ฐ์คํฌ๋ฆฝํธ, CSS, ์ด๋ฏธ์ง ๋ฑ ์ ์  ํ์ผ๋ค์ URL์์ /๋ก ์ค์ ๋ฉ๋๋ค.

9. Basic Information
   : ์๋ฐ์คํฌ๋ฆฝํธ๋ ๋ธ๋ผ์ฐ์ ์ ๋ด์ฅ๋์ด์๋ค!
   Browser๋ HTML์ ๋ถ๋ฌ์ค๊ณ  HTML์ CSS์ JS๋ฅผ ๋ถ๋ฌ์จ๋ค.
   HTML์ด ์ ์ฐฉ์  ๋๋.

---
# Social Login

1. ์์ ๋ก๊ทธ์ธ ๊ธฐ๋ฅ
   : ๋ง์ ์๋น์ค์์ ๋ก๊ทธ์ธ ๊ธฐ๋ฅ์ id/password ๋ฐฉ์๋ณด๋ค๋ ๊ตฌ๊ธ,
   ํ์ด์ค๋ถ, ๋ค์ด๋ฒ ๋ก๊ทธ์ธ๊ณผ ๊ฐ์ ์์ ๋ก๊ทธ์ธ ๊ธฐ๋ฅ์ ์ฌ์ฉํ๋ค.
   ์ด๋ ๋ก๊ทธ์ธ์ ์ง์  ๊ตฌํํ  ๊ฒฝ์ฐ ๋ฐฐ๋ณด๋ค ๋ฐฐ๊ผฝ์ด ์ปค์ง๋ ๊ฒฝ์ฐ๊ฐ
   ๋ง๊ธฐ ๋๋ฌธ์ด๋ค(ํ์ ์๊ฐ)

2. application-oauth.properties  
   : ์ด ํ์ผ์์ scope๋ ๊ธฐ๋ณธ ๊ฐ์ผ๋ก openid, profile, email์ด๋ค. ๊ฐ์ ๋ก profile, email์ ๋ฑ๋กํ ์ด์ ๋ openid๋ผ๋ scope๊ฐ ์์ผ๋ฉด Open Id Provider๋ก ์ธ์ํ๊ธฐ ๋๋ฌธ์๋๋ค. ์ด๋ ๊ฒ ๋๋ฉด OpenId Provider ์ธ ์๋น์ค(๊ตฌ๊ธ)์ ๊ทธ๋ ์ง ์์ ์๋น์ค(๋ค๋น์/์นด์นด์ค ๋ฑ)๋ก ๋๋ ์ ๊ฐ๊ฐ OAuth2Service๋ฅผ ๋ง๋ค์ด์ผํฉ๋๋ค. ํ๋์ OAuth2Service๋ก์ฌ์ฉํ๊ธฐ ์ํด ์ผ๋ถ๋ฌ openid scope๋ฅผ ๋นผ๊ณ  ๋ฑ๋กํฉ๋๋ค.

3. OAuth2
   : OAuth(Open Authentication, Open Authorization)๋ ์ฌ์ฉ์๋ฆฌ์์ค๋ฅผ ๊ด๋ฆฌํ๋ ์๋น์ค(๊ตฌ๊ธ, ํ์ด์ค๋ถ ๋ฑ)์์ ์  3์ ์ ํ๋ฆฌ์ผ์ด์์๊ฒ ์ฌ์ฉ์์ ํจ์ค์๋๋ฅผ ์ ๊ณต ์์ด ์ธ์ฆ, ์ธ๊ฐํ  ์ ์๋ ์ธ์ฆ๊ด๋ จ ํ์ค ํ๋กํ ์ฝ์ด๋ค. OAuth ์ด์ ์ ์ฌ์ฉ์์ ๊ถํ์ ์์๋ฐ๋ ๋ฐฉ์์ ์ฌ์ฉ์๊ฐ ์ด์ฉํ๋ ์๋น์ค์ ๊ณ์ /ํจ์ค์๋๋ฅผ ์ ๊ณต๋ฐ๋ ๋ฐฉ์์ด์๋ค. ์ด๋ ํจ์ค์๋ ์ ์ถ ๋ฟ์๋๋ผ ๊ถํ์ ์์๋ฐ๋ ์ ํ๋ฆฌ์ผ์ด์์ด ํ์ ์ด์์ผ๋ก ๊ณ์ ์ ๋ํ ๋ชจ๋  ๊ถํ์ ํ๋ํ๊ฒ ๋๋ ๋ฑ ๋ค์ํ ๋ฌธ์ ์ ์ด ์กด์ฌํ๋ค. OAuth์ธ์ฆ์ API๋ฅผ ์ ๊ณตํ๋ ์๋ฒ์์ ์ฌ์ฉ์ ์ธ์ฆ ๋ฐ ๊ถํ ๋ถ์ฌ๋ฅผ ์งํํ๊ณ  ์ด์ ๋ํ 'Access Token'์ ๋ฐ๊ธํ๋๋ฐฉ์์ ์ ๊ณตํ๋ฉฐ ์ด๋ฌํ ๋ฌธ์ ๋ค์ ํด๊ฒฐํ  ์ ์๋ค. OAuth2๋ OAuth1 ํ๋กํ ์ฝ์ ๋ณต์กํ ์ธ์ฆ๋ฐฉ์์ ๋จ์ํํ๋ค.
   : ๊ด๋ จ URL : https://mydevstorage.tistory.com/2

4. OAuth2 dependency  
   : spring-boot-starter-oauth2-client๋ ์์ ๋ก๊ทธ์ธ ๋ฑ ํด๋ผ์ด์ธํธ ์์ฅ์์ ์์ ๊ธฐ๋ฅ ๊ตฌํ ์ ํ์ํ ์์กด์ฑ์๋๋ค. spring-boot-starter-oauth2-client์ spring-security-oauth2-jose๋ฅผ ๊ธฐ๋ณธ์ผ๋ก ๊ด๋ฆฌํด์ค๋๋ค.


5. @EnableWebSecurity  
   : Spring Security ์ค์ ๋ค์ ํ์ฑํ์์ผ ์ค๋๋ค.

6. csrf().disable().headers().frameOptions().disable()  
   : h2-console ํ๋ฉด์ ์ฌ์ฉํ๊ธฐ ์ํด ํด๋น ์ต์๋ค์ disableํฉ๋๋ค.

7. authorizeRequests  
   : URL๋ณ ๊ถํ ๊ด๋ฆฌ๋ฅผ ์ค์ ํ๋ ์ต์์ ์์์ ์๋๋ค. authorizeRequests๊ฐ ์ ์ธ๋์ด์ผ๋ง antMatchers์ต์์ ์ฌ์ฉํ  ์ ์์ต๋๋ค.

8. antMatchers  
   : ๊ถํ ๊ด๋ฆฌ ๋์์ ์ง์ ํ๋ ์ต์์๋๋ค. URL, HTTP ๋ฉ์๋๋ณ๋ก ๊ด๋ฆฌ๊ฐ ๊ฐ๋ฅํฉ๋๋ค. "/"๋ฑ ์ง์ ๋ URL๋ค์ permitAll()์ต์์ ํตํด ์ ์ฒด ์ด๋ ๊ถํ์ ์ฃผ์์ต๋๋ค. "/api/v1/**"์ฃผ์๋ฅผ ๊ฐ์ง API๋ USER๊ถํ์ ๊ฐ์ง ์ฌ๋๋ง ๊ฐ๋ฅํ๋๋ก ํ์ต๋๋ค.

9. anyRequest  
   : ์ค์ ๋ ๊ฐ๋ค ์ด์ธ ๋๋จธ์ง URL๋ค์ ๋ํ๋๋๋ค. ์ฌ๊ธฐ์๋ authenticated()์ ์ถ๊ฐํ์ฌ ๋๋จธ์ง URL๋ค์ ๋ชจ๋ ์ธ์ฆ๋ ์ฌ์ฉ์๋ค์๊ฒ๋ง ํ์ฉํ๊ฒ ํฉ๋๋ค. ์ธ์ฆ๋ ์ฌ์ฉ์ ์ฆ, ๋ก๊ทธ์ธํ ์ฌ์ฉ์๋ค์ ์ด์ผ๊ธฐํฉ๋๋ค.

10. logout().logoutSuccessUrl("/")  
    : ๋ก๊ทธ์์ ๊ธฐ๋ฅ์ ๋ํ ์ฌ๋ฌ ์ค์ ์ ์ง์์ ์๋๋ค. ๋ก๊ทธ์์ ์ฑ๊ณต ์ / ์ฃผ์๋ก ์ด๋ํฉ๋๋ค.

11. oauth2Login  
    : OAuth2 ๋ก๊ทธ์ธ ๊ธฐ๋ฅ์ ๋ํ ์ฌ๋ฌ ์ค์ ์ ์ง์์ ์๋๋ค.

12. userInfoEndpoint  
    : OAuth2 ๋ก๊ทธ์ธ ์ฑ๊ณต ์ดํ ์ฌ์ฉ์ ์ ๋ณด๋ฅผ ๊ฐ์ ธ์ฌ ๋ ์ค์ ๋ค์ ๋ด๋น

13. userService  
    : ์์ ๋ก๊ทธ์ธ ์ฑ๊ณต ์ ํ์ ์กฐ์น๋ฅผ ์งํํ  UserService ์ธํฐํ์ด์ค์ ๊ตฌํ์ฒด๋ฅผ ๋ฑ๋กํฉ๋๋ค. ๋ฆฌ์์ค ์๋ฒ(์ฆ, ์์ ์๋น์ค๋ค)์์ ์ฌ์ฉ์ ์ ๋ณด๋ฅผ๊ฐ์ ธ์จ ์ํ์์ ์ถ๊ฐ๋ก ์งํํ๊ณ ์ ํ๋ ๊ธฐ๋ฅ์ ๋ช์ํ  ์ ์์ต๋๋ค.

`CustomOAuth2UserService ํด๋์ค ์ค๋ช`   
// delegate : ๋๋ฆฌ์, ๋ํ, ๋๋ฆฌํ๋ค, ํ๊ฒฌํ๋ค.

1. registrationId
   : ํ์ฌ ๋ก๊ทธ์ธ ์งํ ์ค์ธ ์๋น์ค๋ฅผ ๊ตฌ๋ถํ๋ ์ฝ๋์๋๋ค. ์ง๊ธ์ ๊ตฌ๊ธ๋ง
   ์ฌ์ฉํ๋ ๋ถํ์ํ ๊ฐ์ด์ง๋ง, ์ดํ ๋ค์ด๋ฒ ๋ก๊ทธ์ธ ์ฐ๋ ์์ ๋ค์ด๋ฒ
   ๋ก๊ทธ์ธ์ธ์ง, ๊ตฌ๊ธ ๋ก๊ทธ์ธ์ธ์ง ๊ตฌ๋ถํ๊ธฐ ์ํด ์ฌ์ฉํฉ๋๋ค.

2. userNameAttributeName
   : OAuth2 ๋ก๊ทธ์ธ ์งํ ์ ํค๊ฐ ๋๋ ํ๋๊ฐ์ ์ด์ผ๊ธฐํฉ๋๋ค. PK์ ๊ฐ์ ์๋ฏธ์๋๋ค. ๊ตฌ๊ธ์ ๊ฒฝ์ฐ ๊ธฐ๋ณธ์ ์ผ๋ก ์ฝ๋๋ฅผ ์ง์ํ์ง๋ง, ๋ค์ด๋ฒ์นด์นด์ค ๋ฑ์ ๊ธฐ๋ณธ ์ง์ํ์ง ์์ต๋๋ค. ๊ตฌ๊ธ์ ๊ธฐ๋ณธ ์ฝ๋๋ "sub"์๋๋ค. ์ดํ ๋ค์ด๋ฒ ๋ก๊ทธ์ธ๊ณผ ๊ตฌ๊ธ ๋ก๊ทธ์ธ์ ๋์์ ์ง์ํ  ๋ ์ฌ์ฉํฉ๋๋ค.

3. OAuthAttributes
   : OAuth2UserService๋ฅผ ํตํด ๊ฐ์ ธ์จ OAuth2User์ attribute๋ฅผ๋ด์ ํด๋์ค์๋๋ค. ์ดํ ๋ค์ด๋ฒ ๋ฑ ๋ค๋ฅธ ์์ ๋ก๊ทธ์ธ๋ ์ด ํด๋์ค๋ฅผ์ฌ์ฉํฉ๋๋ค.

4. SessionUser
   : ์ธ์์์ ์ฌ์ฉ์ ์ ๋ณด๋ฅผ ์ ์ฅํ๊ธฐ ์ํ Dto ํด๋์ค์๋๋ค.

`OAuthAttributes ํด๋์ค ์ค๋ช`

1. of()
   : OAuth2User์์ ๋ฐํํ๋ ์ฌ์ฉ์ ์ ๋ณด๋ Map์ด๊ธฐ ๋๋ฌธ์ ๊ฐ ํ๋ํ๋๋ฅผ ๋ณํํด์ผ๋ง ํฉ๋๋ค.

2. toEntity()
   : User ์ํฐํฐ๋ฅผ ์์ฑํฉ๋๋ค. OAuthAttributes์์ ์ํฐํฐ๋ฅผ ์์ฑํ๋ ์์ ์ ์ฒ์ ๊ฐ์ํ  ๋ ์๋๋ค. ๊ฐ์ํ  ๋์ ๊ธฐ๋ณธ ๊ถํ์ GUEST๋ก ์ฃผ๊ธฐ ์ํด์ role ๋น๋๊ฐ์๋ Role.GUEST๋ฅผ ์ฌ์ฉํฉ๋๋ค. OAuthAttributes ํด๋์ค ์์ฑ์ด ๋๋ฌ์ผ๋ฉด ๊ฐ์ ํจํค์ง์ SessionUser ํด๋์ค๋ฅผ ์์ฑํฉ๋๋ค. 

--- 
`index.mustache`  
   : {{#userName}}  
      ๋จธ์คํ์น๋ ๋ค๋ฅธ ์ธ์ด์ ๊ฐ์ if๋ฌธ(if userName != null๋ฑ)์ ์ ๊ณตํ์ง์์ต๋๋ค. true/false ์ฌ๋ถ๋ง ํ๋จํ  ๋ฟ์๋๋ค.๊ทธ๋์ ๋จธ์คํ์น์์๋ ํญ์ ์ต์ข๊ฐ์ ๋๊ฒจ์ค์ผ ํฉ๋๋ค. ์ฌ๊ธฐ์๋ ์ญ์ userName์ด ์๋ค๋ฉด userName์ ๋ธ์ถ์ํค๋๋ก ๊ตฌ์ฑํ์ต๋๋ค.
    
   : a href="/logout"  
	์คํ๋ง ์ํ๋ฆฌํฐ์์ ๊ธฐ๋ณธ์ ์ผ๋ก ์ ๊ณตํ๋ ๋ก๊ทธ์์ URL์๋๋ค. ์ฆ, 
	๊ฐ๋ฐ์๊ฐ ๋ณ๋๋ก ์  URL์ ํด๋นํ๋ ์ปจํธ๋กค๋ฌ๋ฅผ ๋ง๋ค ํ์๊ฐ ์์ต๋๋ค. SecurityConfig ํด๋์ค์์ URL์ ๋ณ๊ฒฝํ  ์ ์์ง๋ง ๊ธฐ๋ณธ URL์ ์ฌ์ฉํด๋ ์ถฉ๋ถํ๋ ์ฌ๊ธฐ์๋ ๊ทธ๋๋ก ์ฌ์ฉํฉ๋๋ค.

   : {{^userName}}  
	๋จธ์คํ์น์์ ํด๋น ๊ฐ์ด ์กด์ฌํ์ง ์๋ ๊ฒฝ์ฐ์๋ ^๋ฅผ ์ฌ์ฉํฉ๋๋ค.
	์ฌ๊ธฐ์๋ userName์ด ์๋ค๋ฉด ๋ก๊ทธ์ธ ๋ฒํผ์ ๋ธ์ถ์ํค๋๋ก ๊ตฌ์ฑํ์ต๋๋ค.

   : a href="oauth2/authorization/google"  
	์คํ๋ง ์ํ๋ฆฌํฐ์์ ๊ธฐ๋ณธ์ ์ผ๋ก ์ ๊ณตํ๋ ๋ก๊ทธ์ธ URL์๋๋ค. 
	๋ก๊ทธ์์ URL๊ณผ ๋ง์ฐฌ๊ฐ์ง๋ก ๊ฐ๋ฐ์๊ฐ ๋ณ๋์ ์ปจํธ๋กค๋ฌ๋ฅผ ์์ฑํ  ํ์๊ฐ
	์์ต๋๋ค.
	
	
`indexController`   
   : (SessionUser) httpSession.getAttribute("user")  
   ์์ ์์ฑ๋ CustomOAuth2UserService์์ ๋ก๊ทธ์ธ ์ฑ๊ณต ์ ์ธ์์ SessionUser๋ฅผ์ ์ฅํ๋๋ก ๊ตฌ์ฑํ์ต๋๋ค. ์ฆ, ๋ก๊ทธ์ธ ์ฑ๊ณต ์ httpSession.getAttribute("user")์์ ๊ฐ์ ๊ฐ์ ธ์ฌ ์ ์์ต๋๋ค.

   : if(user != null)  
	์ธ์์ ์ ์ฅ๋ ๊ฐ์ด ์์ ๋๋ง model์ userName์ผ๋ก ๋ฑ๋กํฉ๋๋ค.
	์ธ์์ ์ ์ฅ๋ ๊ฐ์ด ์์ผ๋ฉด model์ ์๋ฌด๋ฐ ๊ฐ์ด ์๋ ์ํ์ด๋ ๋ก๊ทธ์ธ๋ฒํผ์ด ๋ณด์ด๊ฒ ๋ฉ๋๋ค.

`@LoginUser <- ์ปค์คํ์ผ๋ก ์์ฑํ ์ ๋ธํ์ด์`  
   : @Target(ElementType.PARAMETER)์ด ์ด๋ธํ์ด์์ด ์์ฑ๋  ์ ์๋ ์์น๋ฅผ ์ ์ฅํฉ๋๋ค. PARAMETER๋ก ์ง์ ํ์ผ๋ ๋ฉ์๋์ ํ๋ผ๋ฏธํฐ๋ก ์ ์ธ๋ ๊ฐ์ฒด์์๋ง ์ฌ์ฉํ  ์ ์์ต๋๋ค. ์ด ์ธ์๋ ํด๋์ค ์ ์ธ๋ฌธ์ ์ธ ์ ์๋ TYPE๋ฑ์ด ์์ต๋๋ค.

   : @interface
	์ด ํ์ผ์ ์ด๋ธํ์ด์ ํด๋์ค๋ก ์ง์ ํฉ๋๋ค. LoginUser๋ผ๋ ์ด๋ฆ์ ๊ฐ์ง ์ด๋ธํ์ด์์ด ์์ฑ๋์๋ค๊ณ  ๋ณด๋ฉด ๋ฉ๋๋ค. 

`LoginUserArgumentResolver`  
   : HandlerMethodArgumentResolver ์ธํฐํ์ด์ค๋ฅผ ๊ตฌํํ ํด๋์ค์๋๋ค. HandlerMethodArgumentResolver๋ ํ๊ฐ์ง ๊ธฐ๋ฅ์ ์ง์ํฉ๋๋ค. ๋ฐ๋ก ์กฐ๊ฑด์ ๋ง๋ ๊ฒฝ์ฐ ๋ฉ์๋๊ฐ ์๋ค๋ฉด HandlerMethodArgumentResolver์ ๊ตฌํ์ฒด๊ฐ ์ง์ ํ ๊ฐ์ผ๋ก ํด๋น๋ฉ์๋์ ํ๋ผ๋ฏธํฐ๋ก ๋๊ธธ ์ ์์ต๋๋ค.

   : supportsParameter()
	์ปจํธ๋กค๋ฌ ๋ฉ์๋์ ํน์  ํ๋ผ๋ฏธํฐ๋ฅผ ์ง์ํ๋์ง ํ๋จํฉ๋๋ค. ์ฌ๊ธฐ์๋ ํ๋ผ๋ฏธํฐ์ @LoginUser ์ ๋ธํ์ด์์ด ๋ถ์ด์๊ณ , ํ๋ผ๋ฏธํฐ ํด๋์ค ํ์์ด SessionUser.class์ธ ๊ฒฝ์ฐ true๋ฅผ ๋ฐํํฉ๋๋ค.

   : resolverArgument()
	ํ๋ผ๋ฏธํฐ์ ์ ๋ฌํ  ๊ฐ์ฒด๋ฅผ ์์ฑํฉ๋๋ค. ์ฌ๊ธฐ์๋ ์ธ์์์ ๊ฐ์ฒด๋ฅผ ๊ฐ์ ธ์ต๋๋ค.

`WebConfig`  
   : LoginUserArgumentResolver๊ฐ ์คํ๋ง์์ ์ธ์๋  ์ ์๋๋ก
   WebMvcConfigurer์ ์ถ๊ฐํฉ๋๋ค. HandlerMethodArgumentResolver๋ ํญ์ WebMvcConfigurer์addArgumentResolvers()๋ฅผ ํตํด ์ถ๊ฐํด์ผ ํฉ๋๋ค. ๋ค๋ฅธ HandlerMethodArgumentResolver๊ฐ ํ์ํ๋ค๋ฉด ๊ฐ์ ๋ฐฉ์์ผ๋ก ์ถ๊ฐํด ์ฃผ๋ฉด ๋ฉ๋๋ค.

---
# ์ธ์ ์ ์ฅ์๋ก ๋ฐ์ดํฐ๋ฒ ์ด์ค ์ฌ์ฉํ๊ธฐ
์ง๊ธ ์ฐ๋ฆฌ๊ฐ ๋ง๋  ์๋น์ค๋ ์ ํ๋ฆฌ์ผ์ด์์ ์ฌ์คํํ๋ฉด ๋ก๊ทธ์ธ์ด
ํ๋ฆฝ๋๋ค. ์ด๋ ์ธ์์ด ๋ด์ฅ ํฐ์บฃ์ ๋ฉ๋ชจ๋ฆฌ์ ์ ์ฅ๋๊ธฐ ๋๋ฌธ์๋๋ค.
๊ธฐ๋ณธ์ ์ผ๋ก ์ธ์์ ์คํ๋๋ WAS์ ๋ฉ๋ชจ๋ฆฌ์์ ์ ์ฅ๋๊ณ  ํธ์ถ๋ฉ๋๋ค.
๋ฉ๋ชจ๋ฆฌ์ ์ ์ฅ๋๋ค ๋ณด๋ ๋ด์ฅ ํฐ์บฃ์ฒ๋ผ ์ ํ๋ฆฌ์ผ์ด์ ์คํ ์ ์คํ๋๋
๊ตฌ์กฐ์์  ํญ์ ์ด๊ธฐํ๊ฐ ๋ฉ๋๋ค. ์ฆ, ๋ฐฐํฌํ  ๋๋ง๋ค ํฐ์บฃ์ด ์ฌ์์๋๋
๊ฒ ์๋๋ค. ์ด ์ธ์๋ ํ ๊ฐ์ง ๋ฌธ์ ๊ฐ ๋ ์์ต๋๋ค. 2๋ ์ด์์ ์๋ฒ์์
์๋น์คํ๊ณ  ์๋ค๋ฉด ํฐ์บฃ๋ง๋ค ์ธ์ ๋๊ธฐํ ์ค์ ์ ํด์ผ๋ง ํฉ๋๋ค. ๊ทธ๋์
์ค์  ํ์์์๋ ์ธ์ ์ ์ฅ์์ ๋ํด ๋ค์์ 3๊ฐ์ง ์ค ํ ๊ฐ์ง๋ฅผ ์ ํ
ํฉ๋๋ค.  

  `(1) : ํฐ์บฃ ์ธ์์ ์ฌ์ฉํ๋ค.`  
  : ์ผ๋ฐ์ ์ผ๋ก ๋ณ๋ค๋ฅธ ์ค์ ์ ํ์ง ์์ ๋ ๊ธฐ๋ณธ์ ์ผ๋ก ์ ํ๋๋ ๋ฐฉ์์๋๋ค.
  ์ด๋ ๊ฒ ๋  ๊ฒฝ์ฐ ํฐ์บฃ(WAS)์ ์ธ์์ด ์ ์ฅ๋๊ธฐ ๋๋ฌธ์ 2๋ ์ด์์ WAS๊ฐ
  ๊ตฌ๋๋๋ ํ๊ฒฝ์์๋ ํฐ์บฃ๋ค ๊ฐ์ ์ธ์ ๊ณต์ ๋ฅผ ์ํ ์ถ๊ฐ ์ค์ ์ด ํ์ํฉ๋๋ค.

  `(2) : MySQL๊ณผ ๊ฐ์ ๋ฐ์ดํฐ๋ฒ ์ด์ค๋ฅผ ์ธ์ ์ ์ฅ์๋ก ์ฌ์ฉํ๋ค.`
  : ์ฌ๋ฌ WAS๊ฐ์ ๊ณต์ฉ ์ธ์์ ์ฌ์ฉํ  ์ ์๋ ๊ฐ์ฅ ์ฌ์ด ๋ฐฉ๋ฒ์๋๋ค. ๋ง์
  ์ค์ ์ด ํ์ ์์ง๋ง, ๊ฒฐ๊ตญ ๋ก๊ทธ์ธ ์์ฒญ๋ง๋ค DB IO๊ฐ ๋ฐ์ํ์ฌ ์ฑ๋ฅ์ ์ด์๊ฐ
  ๋ฐ์ํ  ์ ์์ต๋๋ค. ๋ณดํต ๋ก๊ทธ์ธ ์์ฒญ์ด ๋ง์ด ์๋ ๋ฐฑ์คํผ์ค, ์ฌ๋ด ์์คํ
  ์ฉ๋์์ ์ฌ์ฉํฉ๋๋ค.  

  `(3) : Redis, Memcached์ ๊ฐ์ ๋ฉ๋ชจ๋ฆฌ DB๋ฅผ ์ธ์ ์ ์ฅ์๋ก ์ฌ์ฉํ๋ค.` 
   : B2C ์๋น์ค์์ ๊ฐ์ฅ ๋ง์ด ์ฌ์ฉํ๋ ๋ฐฉ์์๋๋ค. ์ค์  ์๋น์ค๋ก ์ฌ์ฉํ๊ธฐ
   ์ํด์๋ Embedded Redis์ ๊ฐ์ ๋ฐฉ์์ด ์๋ ์ธ๋ถ ๋ฉ๋ชจ๋ฆฌ ์๋ฒ๊ฐ ํ์
   ํฉ๋๋ค.

1. spring-session-jdbc
   : ์ธ์ ์ ์ฅ์๋ฅผ ์ฌ์ฉํ  ์ ์๋ build.gradle ๋ฌธ์ฅ

2. spring.session.store-type=jdbc
   : ์ธ์ ์ ์ฅ์๋ฅผ jdbc๋ก ์ ํํ๋๋ก ํ๋ application.properties ๋ฌธ์ฅ

3. src/main ํ๊ฒฝ๊ณผ src/test ํ๊ฒฝ์ ์ฐจ์ด
   : ๋์ ๋ณธ์ธ๋ง์ ํ๊ฒฝ ๊ตฌ์ฑ์ ๊ฐ์ง๋๋ค. ๋ค๋ง, src/main/resources/application .properties๊ฐ ํ์คํธ ์ฝ๋๋ฅผ ์ํํ  ๋๋ ์ ์ฉ๋๋ ์ด์ ๋ test์ application .properties๊ฐ ์์ผ๋ฉด main์ ์ค์ ์ ๊ทธ๋๋ก ๊ฐ์ ธ์ค๊ธฐ ๋๋ฌธ์๋๋ค. ๋ค๋ง, ์๋์ผ๋ก ๊ฐ์ ธ์ค๋ ์ต์์ ๋ฒ์๋ application.properties ํ์ผ๊น์ง์๋๋ค. ์ฆ, application-oauth.properties๋ test์ ํ์ผ์ด ์๋ค๊ณ  ๊ฐ์ ธ์ค๋ ํ์ผ์ ์๋๋ผ๋ ์ ์๋๋ค.

---
# CI์ CD
์ฝ๋ ๋ฒ์  ๊ด๋ฆฌ๋ฅผ ํ๋ VCS ์์คํ(Git, SVN ๋ฑ)์ PUSH๊ฐ ๋๋ฉด ์๋์ผ๋ก ํ์คํธ์ ๋น๋๊ฐ ์ํ๋์ด ์์ ์ ์ธ ๋ฐฐํฌ ํ์ผ์ ๋ง๋๋ ๊ณผ์ ์ CI	(Continuous Integration - ์ง์์  ํตํฉ)๋ผ๊ณ  ํ๋ฉฐ, ์ด ๋น๋ ๊ฒฐ๊ฐ๋ฅผ ์๋์ผ๋ก 	์ด์ ์๋ฒ	์ ๋ฌด์ค๋จ ๋ฐฐํฌ๊น์ง ์งํ๋๋ ๊ณผ์ ์ CD(Continuous Deployment - ์ง์์ ์ธ ๋ฐฐํฌ)๋ผ๊ณ  ํฉ๋๋ค.  
๊ด๋ จ URL : http://bit.ly/2Yv0vFp

![2022-10-26(travis_ci)](https://user-images.githubusercontent.com/96904103/197960112-31fedef8-05de-4071-b965-5ecb0784dfc6.jpg)

1. AWS ๋ฐฐํฌ ์ผํ์ 
- Code Commit
   - ๊นํ๋ธ์ ๊ฐ์ ์ฝ๋ ์ ์ฅ์์ ์ญํ ์ ํฉ๋๋ค.
   - ํ๋ผ์ด๋น ๊ธฐ๋ฅ์ ์ง์ํ๋ค๋ ๊ฐ์ ์ด ์์ง๋ง, ํ์ฌ ๊นํ๋ธ์์ ๋ฌด๋ฃ๋ก ํ๋ผ์ด	๋น ์ง์์ ํ๊ณ  ์์ด์ ๊ฑฐ์ ์ฌ์ฉ๋์ง ์์ต๋๋ค.
- Code Build
   - Travis CI์ ๋ง์ฐฌ๊ฐ์ง๋ก ๋น๋์ฉ ์๋น์ค์๋๋ค.
   - ๋ฉํฐ ๋ชจ๋์ ๋ฐฐํฌํด์ผ ํ๋ ๊ฒฝ์ฐ ์ฌ์ฉํด ๋ณผ๋งํ์ง๋ง, ๊ท๋ชจ๊ฐ ์๋ ์๋น์ค์	์๋ ๋๋ถ๋ถ ์  ํจ์ค/ํ์ํฐ ๋ฑ์ ์ด์ฉํ๋ ์ด๊ฒ ์ญ์ ์ฌ์ฉํ  ์ผ์ด ๊ฑฐ์ ์์ต๋	๋ค.
- CodeDeploy
   - AWS์ ๋ฐฐํฌ ์๋น์ค์๋๋ค.
   - ์์์ ์ธ๊ธํ ๋ค๋ฅธ ์๋น์ค๋ค์ ๋์ฒด์ฌ๊ฐ ์๊ณ , ๋ฑํ ๋์ฒด์ฌ๋ณด๋ค ๋์ ์ ์ด
     ์์ง๋ง, CodeDeploy๋ ๋์ฒด์ฌ๊ฐ ์์ต๋๋ค.
   - ์คํ  ์ค์ผ์ผ๋ง ๊ทธ๋ฃน ๋ฐฐํฌ, ๋ธ๋ฃจ ๊ทธ๋ฆฐ ๋ฐฐํฌ, ๋กค๋ง ๋ฐฐํฌ, EC2 ๋จ๋ ๋ฐฐํฌ ๋ฑ ๋ง์
     ๊ธฐ๋ฅ์ ์ง์ํฉ๋๋ค.

2. travis.yml
- branches
   - Travis CI๋ฅผ ์ด๋ ๋ธ๋์น๊ฐ ํธ์๋  ๋ ์ํํ ์ง ์ง์ ํฉ๋๋ค.
   ํ์ฌ ์ต์์ ์ค์ง master ๋ธ๋์น์ push๋  ๋๋ง ์ํํฉ๋๋ค.

- cache
   - ๊ทธ๋ ์ด๋ค์ ํตํด ์์กด์ฑ์ ๋ฐ๊ฒ ๋๋ฉด ์ด๋ฅผ ํด๋น ๋๋ ํ ๋ฆฌ์ ์บ์ํ์ฌ, ๊ฐ์
   ์์กด์ฑ์ ๋ค์ ๋ฐฐํฌ ๋๋ถํฐ ๋ค์ ๋ฐ์ง ์๋๋ก ์ค์ ํฉ๋๋ค.

- script
   - master ๋ธ๋์น์ ํธ์๋์์ ๋ ์ํํ๋ ๋ช๋ น์ด์๋๋ค.
   - ์ฌ๊ธฐ์๋ ํ๋ก์ ํธ ๋ด๋ถ์ ๋ gradlew์ ํตํด clean & build๋ฅผ ์ํํฉ๋๋ค. 

- notifications
   - Travis CI ์คํ ์๋ฃ ์ ์๋์ผ๋ก ์๋์ด ๊ฐ๋๋ก ์ค์ ํฉ๋๋ค.

- before_deploy
   - deploy ๋ช๋ น์ด๊ฐ ์คํ๋๊ธฐ ์ ์ ์ํ๋ฉ๋๋ค.
   - CodeDeploy๋ Jar ํ์ผ์ ์ธ์ํ์ง ๋ชป ํ๋ฏ๋ก Jar+๊ธฐํ ์ค์  ํ์ผ๋ค์ ๋ชจ์ ์์ถ(zip)ํฉ๋๋ค.

- zip -r SpringWithAWS
  - ํ์ฌ ์์น์ ๋ชจ๋  ํ์ผ์ SpringWithAWS ์ด๋ฆ์ผ๋ก ์์ถ(zip)ํฉ๋๋ค.
  - ๋ช๋ น์ด์ ๋ง์ง๋ง ์์น๋ ๋ณธ์ธ์ ํ๋ก์ ํธ ์ด๋ฆ์ด์ด์ผ ํฉ๋๋ค.

- mkdir -p deploy
  -deploy๋ผ๋ ๋๋ ํ ๋ฆฌ๋ฅผ Travis CI๊ฐ ์คํ ์ค์ธ ์์น์์ ์์ฑํฉ๋๋ค.

- mv SpringWithAWS.zip deploy/SpringWithAWS.zip
     - SpringWithAWS.zip ํ์ผ์ deploy/SpringWithAWS.zip์ผ๋ก ์ด๋์ํต๋๋ค.

- deploy
     - S3๋ก ํ์ผ ์๋ก๋ ํน์ CodeDeploy๋ก ๋ฐฐํฌ ๋ฑ ์ธ๋ถ ์๋น์ค์ ์ฐ๋๋  ํ์๋ค์ ์ ์ธํฉ๋๋ค.

- local_dir: deploy
     - ์์์ ์์ฑํ deploy ๋๋ ํ ๋ฆฌ๋ฅผ ์ง์ ํฉ๋๋ค. ํด๋น ์์น์ ํ์ผ๋ค๋ง S3๋ก ์ ์กํฉ๋๋ค.

3. appspec.yml
- version: 0.0
   - CodeDeploy์ ๋ฒ์ ์ ์ด์ผ๊ธฐํฉ๋๋ค.
   - ํ๋ก์ ํธ ๋ฒ์ ์ด ์๋๋ฏ๋ก 0.0 ์ธ์ ๋ค๋ฅธ ๋ฒ์ ์ ์ฌ์ฉํ๋ฉด ์ค๋ฅ๊ฐ ๋ฐ์ํฉ๋	๋ค.

- source
   - CodeDeploy์์ ์ ๋ฌํด ์ค ํ์ผ ์ค destination์ผ๋ก ์ด๋์ํฌ ๋์์ ์ง์ 
     ํฉ๋๋ค.
   - ๋ฃจํธ ๊ฒฝ๋ก(/)๋ฅผ ์ง์ ํ๋ฉด ์ ์ฒด ํ์ผ์ ์ด์ผ๊ธฐํฉ๋๋ค.

- destination
   - source์์ ์ง์ ๋ ํ์ผ์ ๋ฐ์ ์์น์๋๋ค.
   - ์ดํ Jar๋ฅผ ์คํํ๋ ๋ฑ์ destination์์ ์ฎ๊ธด ํ์ผ๋ค๋ก ์งํ๋ฉ๋๋ค.

- overwrite
   - ๊ธฐ์กด์ ํ์ผ๋ค์ด ์์ผ๋ฉด ๋ฎ์ด์ธ์ง๋ฅผ ๊ฒฐ์ ํฉ๋๋ค.
   - ํ์ฌ yes๋ผ๊ณ  ํ์ผ๋ ํ์ผ๋ค์ ๋ฎ์ด์ฐ๊ฒ ๋ฉ๋๋ค.

- permissions
    - CodeDeploy์์ EC2 ์๋ฒ๋ก ๋๊ฒจ์ค ํ์ผ๋ค์ ๋ชจ๋ ec2-user ๊ถํ์ ๊ฐ๋๋ก ํฉ๋๋ค.
- hooks
    - CodeDeploy ๋ฐฐํฌ ๋จ๊ณ์์ ์คํํ  ๋ช๋ น์ด๋ฅผ ์ง์ ํฉ๋๋ค.
    - ApplicationStart๋ผ๋ ๋จ๊ณ์์ deploy.sh๋ฅผ ec2-user ๊ถํ์ผ๋ก ์คํํ๊ฒ ํฉ๋๋ค.
    - timeout:60 ์ผ๋ก ์คํฌ๋ฆฝํธ ์คํ 60์ด ์ด์ ์ํ๋๋ฉด ์คํจ๊ฐ ๋ฉ๋๋ค.(๋ฌดํ์  ๊ธฐ๋ค๋ฆด ์ ์์ผ๋ ์๊ฐ ์ ํ์ ๋ฌ์ผ๋ง ํฉ๋๋ค.)

4. deploy.sh
- CURRENT_PID
    - ํ์ฌ ์ํ ์ค์ธ ์คํ๋ง ๋ถํธ ์ ํ๋ฆฌ์ผ์ด์์ ํ๋ก์ธ์ค ID๋ฅผ ์ฐพ์ต๋๋ค.
    - ์คํ ์ค์ด๋ฉด ์ข๋ฃํ๊ธฐ ์ํด์์๋๋ค.
    - ์คํ๋ง ๋ถํธ ์ ํ๋ฆฌ์ผ์ด์ ์ด๋ฆ(SpringWithAWS)์ผ๋ก ๋ ๋ค๋ฅธ ํ๋ก๊ทธ๋จ๋ค์ด ์์ ์ ์์ด SpringWithAWS๋ก ๋ jar(pgrep -fl SpringWithAWS | grep.jar)ํ๋ก์ธ์ค๋ฅผ ์ฐพ์ ๋ค ID๋ฅผ ์ฐพ์ต๋๋ค( | awk '{print $1}')

- chmod +x $JAR_NAME
    - Jar ํ์ผ์ ์คํ ๊ถํ์ด ์๋ ์ํ์๋๋ค.
    - nohup์ผ๋ก ์คํํ  ์ ์๊ฒ ์คํ ๊ถํ์ ๋ถ์ฌํฉ๋๋ค.

- $JAR_NAME > $REPOSITORY/nohup.out 2>&1 &
    - nohup ์คํ ์ CodeDeploy๋ ๋ฌดํ ๋๊ธฐํฉ๋๋ค.
    - ์ด ์ด์๋ฅผ ํด๊ฒฐํ๊ธฐ ์ํด nohup.out ํ์ผ์ ํ์ค ์์ถ๋ ฅ์ฉ์ผ๋ก๋ณ๋๋ก ์ฌ์ฉํฉ๋๋ค.
    - ์ด๋ ๊ฒ ํ์ง ์์ผ๋ฉด nohup.out ํ์ผ์ด ์๊ธฐ์ง ์๊ณ , CodeDeploy ๋ก๊ทธ์ ํ์ค ์์ถ๋ ฅ์ด ์ถ๋ ฅ๋ฉ๋๋ค.
    - nohup์ด ๋๋๊ธฐ ์ ๊น์ง CodeDeploy๋ ๋๋์ง ์์ผ๋ ๊ผญ ์ด๋ ๊ฒ ํด์ผ๋ง ํฉ๋๋ค.
