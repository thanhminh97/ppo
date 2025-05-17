🎯 PPO là gì?
PPO (Proximal Policy Optimization) là một thuật toán học chính sách (policy-based) trong học tăng cường sâu (Deep Reinforcement Learning), được phát triển bởi OpenAI năm 2017.

Nó nhằm mục tiêu tối ưu chính sách một cách an toàn và ổn định mà không cần những kỹ thuật quá phức tạp như trong TRPO (Trust Region Policy Optimization).

⚙️ PPO hoạt động như thế nào?
Thu thập dữ liệu bằng cách chạy chính sách hiện tại trong môi trường và lưu lại: trạng thái, hành động, phần thưởng, v.v.

Ước lượng lợi ích (advantage) cho mỗi hành động (thường dùng GAE – Generalized Advantage Estimation).

Cập nhật chính sách bằng cách tối ưu hàm mất mát PPO – một phiên bản clip của hàm chính sách để giới hạn thay đổi chính sách quá đột ngột.

Hàm mất mát chính sách của PPO:

𝐿
clip
(
𝜃
)
=
𝐸
𝑡
[
min
⁡
(
𝑟
𝑡
(
𝜃
)
𝐴
^
𝑡
,
  
clip
(
𝑟
𝑡
(
𝜃
)
,
1
−
𝜖
,
1
+
𝜖
)
𝐴
^
𝑡
)
]
L 
clip
 (θ)=E 
t
​
 [min(r 
t
​
 (θ) 
A
^
  
t
​
 ,clip(r 
t
​
 (θ),1−ϵ,1+ϵ) 
A
^
  
t
​
 )]
𝑟
𝑡
(
𝜃
)
=
𝜋
𝜃
(
𝑎
𝑡
∣
𝑠
𝑡
)
𝜋
𝜃
old
(
𝑎
𝑡
∣
𝑠
𝑡
)
r 
t
​
 (θ)= 
π 
θ 
old
​
 
​
 (a 
t
​
 ∣s 
t
​
 )
π 
θ
​
 (a 
t
​
 ∣s 
t
​
 )
​
 : tỷ lệ xác suất mới/cũ.

𝐴
^
𝑡
A
^
  
t
​
 : lợi ích (advantage).

𝜖
ϵ: hệ số clip (thường ~0.1–0.2).

✅ Ưu điểm của PPO
Ổn định và hiệu quả cao trong thực nghiệm.

Dễ triển khai, không cần tính đạo hàm bậc 2 như TRPO.

Phổ biến rộng rãi trong các bài toán như chơi game, robot, mô phỏng…

📌 Ứng dụng
Game Atari (Breakout, Pong, v.v.)

Môi trường 3D như Unity, MuJoCo, OpenAI Gym

Điều khiển robot

Mô phỏng tài chính, y tế, giao thông...
