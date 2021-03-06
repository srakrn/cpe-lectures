# Algorithm (24 Jan)
Today's topics: Big-O, Big-\\(\omega\\), Big-\\(\theta\\)

## Big-O Notation

ปกติจะเทียบกับขนาดของข้อมูลตั้งต้น (อินพุท) โดย Big-O __แสดง Upper bound ของ function__

![Big-O chart](graphs/big_o_chart.svg)

<div class='alert alert-primary'>
<b>การพิสูจน์ Big-O</b>: เราจะแสดงว่าฟังก์ชั่น $f(n)$ มี Big-O เป็น $\mathcal{O}(g(n))$ ด้วยการพิสูจน์ upper bound กล่าวคือ

\begin{align} f(n) \leq c \cdot g(n) \quad \forall n \geq k \end{align}
</div>

<div class='alert alert-success'>
<b>Tips</b> เราจะไม่สนใจค่าคงที่ที่อยู่ในการคำนวน Big-O (เช่น $f(n) = 2n$ เราจะบอกว่าเป็น Big-O ของ $\mathcal{O}(n)$ โดยไม่สนใจเลข 2 ข้างหน้า<br/><br/>

ดังนั้นในการพิสูจน์ Big-O เราจึงไม่จำเป็นจะต้องสนใจค่าคงที่ในสมการเลย
</div>

<div class='alert alert-warning'>
<b>Example</b>: จงแสดงว่า $ 4n^2 + 2n$ มี Big-O เป็น $\mathcal{O}(n^2)$
<br/>
<b>Solution</b>:
เพราะ
\begin{align}4n^2 \leq 4n^2 \quad \forall n \geq 1\end{align}
\begin{align}2n \leq n^2 \quad \forall n \geq 1\end{align}
ดังนั้นจากสองสมการบวกกัน
\begin{align}4n^2 + 2n \leq 5n^2 \quad \forall n \geq 2\end{align}
ตัดทอนค่าคงที่
\begin{align}4n^2 + 2n \leq n^2 \quad \forall n \geq 2\end{align}
</div>

## Big-Omega Notation

Big-Omega __แสดง lower bound ของฟังก์ชั่น__

<div class='alert alert-primary'>
<b>การพิสูจน์ Big-$\Omega$</b>: เราจะแสดงว่าฟังก์ชั่น $f(n)$ มี Big-$\Omega$ เป็น $\Omega(g(n))$ ด้วยการพิสูจน์ lower bound กล่าวคือ

\begin{align} f(n) \geq \cdot g(n) \quad \forall n \geq k \end{align}

สังเกตว่าเราเปลี่ยนมาพิสูจน์ว่า $f(n)$ กินเวลา<b>นานกว่า</b> $g(n)$
</div>

<div class='alert alert-success'>
<b>Tips</b> เราจะไม่สนใจค่าคงที่ที่อยู่ในการคำนวนเช่นกัน
</div>

<div class='alert alert-warning'>
<b>Example</b>: จงแสดงว่า $ 4n^2 + 2n$ มี Big-$\Omega$ เป็น $\Omega(n)$
<br/>
<b>Solution</b>:
เพราะ
\begin{align}4n^2 \geq n \quad \forall n \geq 1\end{align}
\begin{align}2n \geq n \quad \forall n \geq 1\end{align}
ดังนั้นจากสองสมการบวกกัน
\begin{align}4n^2 + 2n \geq 2n^2 \quad \forall n \geq 2\end{align}
ตัดทอนค่าคงที่
\begin{align}4n^2 + 2n \geq n^2 \quad \forall n \geq 2\end{align}
</div>

อันที่จริงแล้ว สำหรับเฉลยข้อข้างบน เราสามารถพยายามเพิ่ม Big-Omega ไปได้ถึง $\Omega(n^2)$

<div class='alert alert-warning'>
<b>Example</b>: จงแสดงว่า $ 4n^2 + 2n$ มี Big-$\Omega$ เป็น $\Omega(n^2)$
<br/>
<b>Solution</b>:
เพราะ
\begin{align}4n^2 \geq n^2 \quad \forall n \geq 1\end{align}
\begin{align}2n \geq 0 \quad \forall n \geq 1\end{align}
ดังนั้นจากสองสมการบวกกัน
\begin{align}4n^2 + 2n \geq n^2 \quad \forall n \geq 2\end{align}
</div>

## Big-Theta Notation

ถ้า $f(n)$ มี Big-O เป็น $\mathcal{O}(g(n))$ และมี Big-Omega เป็น $\Omega(g(n))$ __จะได้ว่า $f(n)$ มี Big-Theta เป็น $\Theta(g(n))$__

<div class='alert alert-success'>
<b>Tips</b> เราจะไม่สนใจค่าคงที่ที่อยู่ในการคำนวนเช่นกัน
</div>

<div class='alert alert-warning'>
<b>Example</b>: จงแสดงว่า $ 4n^2 + 2n$ มี Big-$\Omega$ เป็น $\Omega(n)$
<br/>
<b>Solution</b>:
เพราะทำ Big-O และ Big-Omega ได้ $\mathcal{O}(n^2)$ และ $\Omega(n^2)$ ทั่งคู่ ดังนั้นจะได้ Big-Theta เป็น $\Theta(n^2)$ ด้วย
</div>\cdot 
