Machine learning - Linear Regression

Bài toán dự tính giá nhà dựa trên diện tích là bài toán đầu tiên khi tôi bắt đầu học về ML. Với dữ liệu có sẵn bao gồm diện tích và giá nhà, bài toán yêu cầu dự đoán giá nhà khi biết diện tích.
Bài toán thật đơn giản nếu như mỗi nhà có cùng giá với một đơn vị diện tích.
Như vậy chỉ cần tìm đơn giá của 1 đơn vị diện tích:
Đơn giá = Giá tiền / Diện tích

Đối với việc tính giá nhà về sau chỉ cần lấy tích của Đơn giá và Diện tích.
Giá tiền = Đơn giá * Diện tích

Thật đơn giản phải không? Nhưng đời không như là mơ, mỗi căn nhà lại có đơn giá trên diện tích khác nhau.Như vậy phải dự toán làm sao để gần đúng nhất.Giá nhà dự đoán sẽ là một hàm số bậc nhất với diện tích.
Trong dữ liệu về nhà có sẵn (dùng để training), với diện tích xᵢ thì giá nhà sẽ là yᵢ. i chạy từ 1 đến m ( 1<= i <= m ).

Giả định hàm số cần tìm là hθ(ｘ) = θ₀　+　θ₁x
Và để dự đoán chính xác thì hàm số này phải đi qua hoặc gần với điểm (x,y) trên trục tọa độ.
tổng quát
h(xᵢ) = θ₀　+　θ₁xᵢ (i là số nguyên dương 1<= i <= m )
cần tìm θ₀　+　θ₁ sao cho khi thay thế xᵢ thì giá trị hàm số gần yᵢ nhất

Ta thêm x₀ = 1 vào phương trình để dễ xử lý.
Hàm số sẽ trở thành:
h(xᵢ) = θ₀x₀　+　θ₁xᵢ ( <=> [x₀, x₁, ..., xₘ] + [θ₀,θ₁] )

để h(x) gần y nhất thì chính là việc tính cost nhỏ nhất. 
Ta đặt cost function J(θ)
------------------m 
    J(θ) = 1/2m * Σ  (hθ(xᵢ)-yᵢ)²
------------------i=1

Để tìm ra theta thích hợp trong bài toán trên thì ta dùng thuật toán Gradient Descent.
Thuật toán này thực hiện như sau:
1. Chọn một điểm bắt đầu của theta (θ₀) 
    θ = θ₀
2. Thay đổi giá trị của theta(θ) đến khi giá trị của J(θ) là đủ nhỏ và theta không đổi 
    mỗi một lần thay đổi giá trị của theta sẽ giảm α*(d/dθʲ)J(θ)
    (α được gọi là learning rate)

Ở đây cần giới hạn số lần thay đổi thích hợp để tính ra được theta tương đối hợp lý.
Số lần lặp (iterator) và α được chỉ định. Ở mức cơ bản này thì cần chạy thử để dự đoán được iterator và learning rate hợp lý.
