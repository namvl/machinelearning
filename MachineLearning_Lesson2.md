### Linear Regression with Multiple Variables  


1. Multiple Features  
> Linear regression with multiple variables is also known as "multivariate linear regression".  

Quay trở lại với bài toán giá nhà, trên thực tế việc dự đoán giá nhà không chỉ phụ thuộc vào diện tích, nó còn phụ thuộc bởi rất nhiều yếu tố khác. Có thể kể đến như mặt tiền bao nhiêu mét, sâu bao nhiêu mét, cao mấy tầng, có bao nhiêu phòng ngủ, có gần ga tàu không ...  
Mỗi một yếu tố ảnh hưởng đến kết quả giá nhà được coi như là một feature.  

Giả sử mỗi feature kể trên được biểu thị từ x<sub>1</sub> đến x<sub>n</sub> thì hàm dự đoán hθ sẽ như sau:  

h<sub>θ</sub>(x) = θ<sub>0</sub> + θ<sub>1</sub>x<sub>1</sub> + θ<sub>2</sub>x<sub>2</sub> + ... + θ<sub>n</sub>x<sub>n</sub>

Trong đó θ<sub>0</sub> giá nhà cơ bản, θ<sub>1</sub>giá nhà trên 1m<sup>2</sup>, θ<sub>2</sub> giá nhà trên số phòng... x<sub>1</sub> sẽ là diện tích, x<sub>2</sub> sẽ là số phòng ...

đặt x<sub>0</sub>=1 ta có hàm giả định mới như sau:

h<sub>θ</sub>(x) = θ * X  

X = [x<sub>0</sub>; x<sub>1</sub>; ...; x<sub>n</sub>]  
θ = [θ<sub>0</sub>, θ<sub>1</sub>, ..., θ<sub>n</sub>]  

* x<sup>(i)</sup><sub>0</sub>=1  

x<sup>(i)</sup><sub>j</sub>=giá trị feature j ở dòng thứ i<sup>th</sup> trong dữ liệu training  
x<sup>(i)</sup>=the input (features) của dòng thứ i<sup>th</sup> trong dữ liệu training  
m=số lần train  
n=số lượng features  



2. Gradient Descent for Multiple Variables  
Trong bài toán quy hồi tuyến tính với 1 biến (linear regression with one variable) chúng ta chỉ có tính toán với θ<sub>0</sub> và θ<sub>1</sub>.
Trong bài toán này chúng ta sẽ tính với θ<sub>0</sub> cho đến θ<sub>n</sub>.

![alt text](/img/lesson2_001.JPG "~~")

Đơn giản hóa thành
![alt text](/img/lesson2_002.JPG "Tổng quát")

3. Gradient Descent in Practice - Feature Scaling, Learning rate  

Khi triển khai bài toán, có thể chúng ta nhận được những dữ liệu dùng để train có sự sai lệch lớn, một feature có giá trị từ 0 đến 1, một feature khác lại từ 100 đến 10000 chẳng hạn. Trong trường hợp đó cần phải chuẩn hóa lại dữ liệu.  

Chúng ta sẽ sử dụng 2 kỹ thuật là Feature scaling và mean normalization để chuẩn hóa dữ liệu.
Feature scaling chia input theo phạm vi của dữ liệu(ví dụ: lấy giá trị lớn nhất trừ đi giá trị nhỏ nhất), kết quả sẽ nằm trong khoảng mới giá trị là 1.  
Mean value (μ) là giá trị trung bình của các input variables.  
Implement 2 kỹ thuật trên bằng công thức toán học sau:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x<sub>i</sub>-μ<sub>i</sub>  
x<sub>i</sub>:=―――  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;s<sub>i</sub>  
μ<sub>i</sub>　là trung bình giá trị của feature i.  
s<sub>i</sub> là khoảng chênh lệch giữa giá trị lớn nhất và nhỏ nhất của feature i.  

ví dụ:  
Cho test data như dưới  
| midterm exam | (midterm exam)<sup>2</sup> | Final exam |
|-|-|-|
|89|7921|96|
|72|5148|74|
|94|8836|87|
|69|4761|78|

Tính Normalied x<sup>3</sup><sub>2</sup>  
x<sup>3</sup><sub>2</sup> = 8836
μ<sub>2</sub> = (x<sup>1</sup><sub>2</sup> + x<sup>2</sup><sub>2</sup> + x<sup>3</sup><sub>2</sup> + x<sup>4</sup><sub>2</sup>)/4 = (7921+5148+8836+4761)/4 = 6675,5  
s<sub>2</sub> = 8836 - 4761 = 4075  

=> Normalized của x<sup>3</sup><sub>2</sup> = ( 8836 - 6675,5 ) / 4075 = 0,53 

