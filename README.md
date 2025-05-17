Proximal Policy Optimization (PPO)

Đây là kho mã triển khai thuật toán Proximal Policy Optimization (PPO) — một trong những phương pháp học tăng cường phổ biến và hiệu quả, được phát triển bởi OpenAI.

🔍 Giới thiệu

PPO là một thuật toán học chính sách dựa trên chính sách gradient (policy gradient), mục tiêu là tối ưu chính sách một cách ổn định và hiệu quả, tránh các cập nhật quá lớn có thể làm phân tán chính sách.

⚙️ Cách hoạt động

Thu thập dữ liệu: Chạy chính sách hiện tại trong môi trường và ghi lại các trải nghiệm (trạng thái, hành động, phần thưởng).

Ước tính lợi ích (Advantage): Tính giá trị lợi ích ̂ cho mỗi hành động, thường dùng GAE (Generalized Advantage Estimation).

Cập nhật chính sách: Tối ưu hàm mất mát PPO với cơ chế clipping để giới hạn mức thay đổi của chính sách.


📚 Tham khảo

Schulman et al., Proximal Policy Optimization Algorithms (2017): https://arxiv.org/abs/1707.06347

OpenAI Spinning Up PPO Tutorial: https://spinningup.openai.com/en/latest/algorithms/ppo.html

