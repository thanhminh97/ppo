Proximal Policy Optimization (PPO)

Đây là kho mã triển khai thuật toán Proximal Policy Optimization (PPO) — một trong những phương pháp học tăng cường phổ biến và hiệu quả, được phát triển bởi OpenAI.

🔍 Giới thiệu

PPO là một thuật toán học chính sách dựa trên chính sách gradient (policy gradient), mục tiêu là tối ưu chính sách một cách ổn định và hiệu quả, tránh các cập nhật quá lớn có thể làm phân tán chính sách.

⚙️ Cách hoạt động

Thu thập dữ liệu: Chạy chính sách hiện tại trong môi trường và ghi lại các trải nghiệm (trạng thái, hành động, phần thưởng).

Ước tính lợi ích (Advantage): Tính giá trị lợi ích ̂ cho mỗi hành động, thường dùng GAE (Generalized Advantage Estimation).

Cập nhật chính sách: Tối ưu hàm mất mát PPO với cơ chế clipping để giới hạn mức thay đổi của chính sách.

📐 Công thức hàm mất mát

L^{\text{clip}}(\theta) = \mathbb{E}_t \big[ \min \big( r_t(\theta) \hat{A}_t,\; \mathrm{clip}(r_t(\theta),1-\epsilon,1+\epsilon) \hat{A}_t \big) \big]

: Tỷ lệ xác suất thực hiện hành động theo chính sách mới so với chính sách cũ.

: Ước tính lợi ích, thể hiện độ tốt hơn của hành động so với mức trung bình.

: Tham số clip, thường đặt khoảng 0.1–0.2 để giới hạn  trong [1−ε, 1+ε].

Hàm clip giúp ngăn không cho policy update vượt quá vùng an toàn, giữ ổn định quá trình huấn luyện.

🛠 Cài đặt

# Tạo môi trường ảo và cài đặt các thư viện cần thiết
git clone <đường dẫn repo>
cd <tên thư mục>
python3 -m venv venv
source venv/bin/activate  # Linux/Mac
venv\\Scripts\\activate  # Windows
pip install -r requirements.txt

requirements.txt của bạn có thể bao gồm:

torch
gym
numpy

🚀 Sử dụng

Chạy huấn luyện PPO trên môi trường CartPole-v1:

python train_ppo.py --env CartPole-v1

Tuỳ chỉnh tham số hyperparameter trong file cấu hình hoặc dòng lệnh.

📚 Tham khảo

Schulman et al., Proximal Policy Optimization Algorithms (2017): https://arxiv.org/abs/1707.06347

OpenAI Spinning Up PPO Tutorial: https://spinningup.openai.com/en/latest/algorithms/ppo.html

