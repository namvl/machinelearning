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

X = [x<sub>0</sub>; x<sub>1</sub>; ..., x<sub>n</sub>]  
θ = [θ<sub>0</sub>, θ<sub>1</sub>, ..., θ<sub>n</sub>]  

* x<sup>(i)</sup><sub>0</sub>=1  

x<sup>(i)</sup><sub>j</sub>=giá trị feature j ở dòng thứ i<sup>th</sup> trong dữ liệu training  
x<sup>(i)</sup>=the input (features) của dòng thứ i<sup>th</sup> trong dữ liệu training  
m=số lần train  
n=số lượng features  



2. Gradient Descent for Multiple Variables  


