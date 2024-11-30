# Project IOT - M05: Light Controlling Using Hand Gestures

## I. Giới thiệu
**Hand Gestures Recognition** là một lĩnh vực quan trọng trong tương tác người và máy, cho phép hệ thống hiểu và phản hồi lại các động tác tay của người dùng. Công nghệ này dựa trên việc phân tích hình ảnh hoặc video để xác định vị trí và hình dạng của bàn tay, từ đó nhận diện các cử chỉ cụ thể.

Các bước chính trong nhận diện cử chỉ tay:
- Phát hiện bàn tay: Xác định vị trí của bàn tay trong khung hình bằng các kỹ thuật xử lý ảnh.
- Trích xuất đặc trưng: Thu thập thông tin về hình dạng, vị trí các ngón tay, góc độ, v.v.
- Phân loại cử chỉ: Sử dụng các mô hình học máy để phân loại cử chỉ dựa trên các đặc trưng đã trích xuất.

Ứng dụng của nhận diện cử chỉ tay:
- Điều khiển thiết bị: Tương tác với máy tính, điện thoại, hoặc các thiết bị thông minh mà không cần chạm.
- Thực tế ảo và tăng cường: Cải thiện trải nghiệm người dùng trong môi trường ảo.
- Hỗ trợ người khuyết tật: Giúp người khuyết tật vận động hoặc giao tiếp dễ dàng hơn.

**Công nghệ MediaPipe của Google:** MediaPipe là một framework mã nguồn mở cung cấp các giải pháp tiên tiến cho xử lý đa phương tiện thời gian thực. MediaPipe Gesture Recognizer là một trong những giải pháp mạnh mẽ cho nhận diện cử chỉ tay, với khả năng:
- Nhận diện chính xác: Cung cấp mô hình tiên tiến với độ chính xác cao
- Thực tế ảo và tăng cường: Cải thiện trải nghiệm người dùng trong môi trường ảo.
- Hỗ trợ người khuyết tật: Giúp người khuyết tật vận động hoặc giao tiếp dễ dàng hơn.

## II. Chạy chương trình
### 1. Định nghĩa class: 
Định nghĩa các class trong file `hand_gesture.yaml`.
### 2. Thu thập dữ liệu: 
- di chuyển vào đúng thư mục chứa file `generate_landmark_data.py`
- Mở `terminal` và chạy lệnh `python generate_landmark_data.py` để chạy chương trình thu thập dữ liệu
- Nhấn các phím 'a' để ghi dữ liệu cho cử chỉ có class 0 đã định nghĩa trong file `hand_gesture.yaml`. Để kết thúc ghi dữ liệu nhấn lại phím 'a'.
- Tương tự đối với các class tiếp theo, các phím sẽ bắt đầu từ 'b',...
- Chương trình sẽ thu thập 3 lần cho 3 tập train, val, test. Thu xong các class trong file `hadn_gesture.yaml` cho tập train, nhấn 'q' để thoát chương trình thu cho tập train. Chương trình thu cho tập val sẽ được tự động mở lên, tiếp tục thu cho đến tập test.
### 3. Training mô hình: 
Sử dụng dữ liệu vừa thu thập được để huấn luyện mô hình MLP trong file `models/hand_gesture_recognition.ipynb`
### 4. Triển khai mô hình: 
Sử dụng file trọng số mô hình vừa train xong để thực hiện điều khiển đèn tương ứng.

Chạy file `detect_simulation.py` để mô phỏng điều khiển đèn bằng cử chỉ tay trong điều kiện không có thiết bị thật.