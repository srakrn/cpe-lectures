# Discrete for Quiz 1 Survival
เขียนเท่าที่ไอ้แทนจะมีปัญญาก่อนตาย

## Recursive modelling
### Josephus Problem
มีคน n คน ฆ่าทีละ k คน จะสามารถยุบไปได้เรื่อยๆ โดยใช้ความสัมพันธ์ดังนี้

- $f(2n) = 2f(n)-1$
- $f(2^n) = 1$ สำหรับ $n=0,1,2,3,4...$
- $f(2n+1) = 2f(n)+1$

### เกมไม้ขีด
มีไม้ขีด 10 อัน เอาออกได้ทีละ 1,2,3 อัน จะทำยังไงให้ชนะ?   
คำตอบ: พยายามเอาไม้ขีดออกให้จำนวนไม้ขีดเหลือในรูปของ $4k+1$

ถ้าสมมติเหลือไม้ขีด 5 อันในตาศัตรู ($4k+1, k=1$) จะพบว่าเราสามารถคุมเกมให้เหลือไม้ขีดอันเดียวในตาฝ่ายตรงข้ามได้เสมอ

*คำถาม: ถ้าเป็นหยิบได้มากสุดทีละ 5 ล่ะ?*
### การเขียนลำดับ
เราสามารถเขียนลำดับได้ในรูปสองแบบ คือรูปปิด และรูป recursive

- รูปปิด คือมีแค่เทอมของ n สำหรับลำดับที่ n เช่น $a_n = 2n-1$ คือลำดับ 1,3,5,7,9,...
- รูป recursive คือพูดถึงเทอมต้นๆ ของ $a_n$ และอิงลำดับต่อๆ ไป เช่น $a_n = a_{n-1}+2$ เมื่อ $a_1 = 1$

**Example** เขียน $a_n=2^n$ ให้อยู่ในรูป recursive

Solution: จะพบว่า

- 2^1 = 1
- 2^2 = 4 = 1+3 = $a_1+3$
- 2^3 = 9 = 4+5 = $a_2+5$
- 2^4 = 16 = 9+7 = $a_3+7$

ดังนั้น $a_1 = 1$ และ $a_n = a_{n-1}+(2n-1)$

**Example** แปลง $a_1 = 2$ และ $a_n=3a_{n-1}$ เป็นรูปปิด

Solution:

- $a_1$ = 2
- $a_2$ = $2\times3$
- $a_3$ = $2\times3^2$

ดังนั้น $a_n = 2\times3^{n-1}$

## ปัญหาขึ้นบันได
บันไดขึ้นได้ทีละ 1-2 ขั้น

จะสามารถมอง subproblem ของการขึ้นบันได n ขั้นได้เป็น

$$ วิธีขึน 1 ขั้น * (การขึ้นบันได n-1 ขั้น) + วิธีขึ้น 2 ขั้น * (การขึ้นบันได n-2 ขั้น) $$

ดังนั้น $f(n) = f(n-1)+f(n-2)$ ทั้งนี้ $f(1)=f(2)=1$

## Propositional logic
### ปัญหาชายตอแหล

A บอกว่า "มีคนตอแหล 1 คนเป๊ะๆ" B บอกว่า "มีอย่างน้อย 1 คนไม่ตอแหล" ถามว่าใครตอแหลมั่ง

เราอาจทดลองให้ p และ q เป็นชายที่ตอแหละและไม่ตอแหล ไล่ความเป็นไปได้ทั้งหมดของ p,q ที่เท่ากับจริงและเท็จ ก่อนเอาไปใส่ตารางความจริง 

![img_1.PNG](img_1.PNG)

จากตารางนี้เราจะพบว่า
- ไม่ตอแหลทั้งสองคน เป็นไปไม่ได้ เพราะจะแย้งกับที่บอกว่า "มีตอแหลหนึ่งคน"
- B ตอแหล เป็นไปไม่ได้ เพราะ B บอกว่ามีอย่างน้อยหนึ่งคนที่พูดจริง ซึ่งมันก็ไม่ได้ตอแหล แต่ B ตอแหล ดังนั้นเป็นไปไม่ได้
- A ตอแหล เป็นไปไม่ได้ เพราะ A บอกว่าหนึ่งคนที่ตอแหล แต่ A ก็พูดจรืง ขัดแย้งกับที่เดาว่า A ตอแหล
- สรุป ตอแหลทั้งคู่

**ถ้างง เช็คว่าไล่ค่าอันไหนแล้วมันออกมาเหมือนกัน ในที่นี้แถวสุดท้ายทั้งฝั่ง p,q และ statement 1,2 เหมือนกัน**

*Problem: ถ้ามีสามคน บอกว่า "หนี่งคนเป๊ะๆ ไม่ตอแหล" "ตอแหลทุกคน" "สองคนแรกนั่นตอแหล" ใครตอแหลบ้าง?*

### The logic of proposition
ประโยคใดๆ จะเป็นประพจน์ (proposition) ได้ถ้าระบุค่าความจริงได้ชัดเจน

#### ตัวดำเนินการทางประพจน์
- $\land$ and
- $\lor$ or
- $\neg$ หรือ $\sim$ นิเสธ (negation)

#### กฏของเดอร์มอร์กอง
แจกนิเสธเข้า and or กลับเครื่องหมาย
- $\neg(p \land q) \simeq \neg p \lor \neg q$
- $\neg(p \lor q) \simeq \neg p \land \neg q$

#### Tautology/Contradiction
สัจนิรันดร์ (tautology) คือจริงเสมอ ตอแหลนิรันดร์ (contradiction -- เออ กูไม่รู้ชื่อไทย) คือเท็จเสมอ

### Predicates
คือ statement $P(x)$ ที่จับ x ยัดเข้าไปแล้วสามารถบอกได้ว่าจริงหรือเท็จ

เช่น $P(x)$ แทนด้วย $x\gt15$ จะพบว่า
- แทน x เป็น 10 จะได้เท็จ
- แทน x เป็น 20 จะได้จริง

#### For all, for some (Quantified statement)
$\forall$ คือ for all ส่วน $\exists$ คือ for some/exist

เช่น ประโยคว่า สำหรับจำนวน r **ทุกตัว**ในจำนวนนับ r หาร 1 ได้ r สามารถเขียนเป็น

$$\forall r \in R, r \div 1 = r$$

ประโยคนี้เป็นจริง เพราะ $r\div1 = r$ อยู่แล้ว (เอกลักษณ์การหาร)

ในขณะที่ประโยคว่า สำหรับจำนวน r **ทุกตัว**ในจำนวนนับ r เป็นจำนวนคี่ สามารถเขียนเป็น

$$\forall r \in R, r \in O$$

จะพบว่าเป็นเท็จ เพราะมี 2 ที่ไม่เป็นจำนวนคี่

**จะพิสูจน์ว่าประโยค for all เป็นเท็จ แค่หาตัวแย้งว่ามีตัวที่ไม่เป็นไปตามเงื่อนไข**

##### นิเสธของ Quantified statement

- $\neg(\forall x \in D, P(x)) \simeq \exists x \in D, \neg P(x)$
- $\neg(\exists x \in D, P(x)) \simeq \forall x \in D, \neg P(x)$
