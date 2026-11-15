# THEORY: PYTHON ENVIRONMENTS, VIRTUAL MACHINES, CONTAINERS AND GIT/GITHUB

## 1. PYTHON ENVIRONMENT MANAGEMENT

### 1.1. Python Environment là gì?

Python Environment (môi trường Python) là môi trường chứa trình thông dịch Python, các thư viện và những công cụ cần thiết để chạy chương trình Python.

Trong quá trình phát triển phần mềm, mỗi dự án có thể yêu cầu phiên bản Python và các thư viện khác nhau. Nếu tất cả dự án sử dụng chung một môi trường, việc cài đặt hoặc cập nhật thư viện có thể gây xung đột giữa các dự án.

Vì vậy, việc quản lý môi trường Python giúp:
- Cô lập các thư viện giữa những dự án khác nhau.
- Tránh xung đột phiên bản thư viện.
- Dễ dàng tái tạo môi trường làm việc.
- Giúp dự án hoạt động ổn định trên nhiều máy tính.

### 1.2. Virtual Environment là gì?

Virtual Environment (môi trường ảo Python) là một môi trường Python độc lập, được tạo ra để mỗi dự án có thể quản lý các thư viện và dependencies riêng.

Virtual Environment không phải là một máy tính ảo và cũng không cài đặt một hệ điều hành riêng. Nó chủ yếu giúp cô lập các package Python.

Ví dụ:

- Project A sử dụng NumPy phiên bản 2.2.6.
- Project B sử dụng NumPy phiên bản 1.26.

Hai dự án có thể sử dụng hai môi trường riêng biệt mà không ảnh hưởng đến nhau.

**Ưu điểm:**
- Cô lập dependencies giữa các dự án.
- Hạn chế xung đột thư viện.
- Dễ dàng quản lý và tái tạo môi trường.
- Tiết kiệm tài nguyên hơn so với việc tạo máy ảo hoàn chỉnh.

**Hạn chế:**
- Không cô lập hệ điều hành.
- Không cung cấp một hệ thống phần cứng ảo hoàn chỉnh.
- Các môi trường thường vẫn phụ thuộc vào hệ điều hành máy chủ.

### 1.3. Các công cụ quản lý môi trường Python

#### a. venv

`venv` là module được tích hợp sẵn trong Python, cho phép tạo môi trường ảo cho từng dự án.

Ví dụ:

Tạo môi trường:

```bash
python -m venv .venv
```

Kích hoạt trên Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

Cài đặt thư viện:

```bash
pip install numpy
```

Kiểm tra các thư viện:

```bash
pip list
```

Thoát khỏi môi trường:

```bash
deactivate
```

#### b. virtualenv

`virtualenv` là một công cụ bên thứ ba dùng để tạo và quản lý môi trường Python độc lập.

Cài đặt:

```bash
pip install virtualenv
```

Tạo môi trường:

```bash
virtualenv .venv
```

Kích hoạt trên Windows:

```powershell
.\.venv\Scripts\Activate.ps1
```

virtualenv có chức năng tương tự venv nhưng cung cấp thêm một số tính năng và khả năng tương thích với nhiều phiên bản Python khác nhau.

#### c. pyenv

`pyenv` là công cụ quản lý nhiều phiên bản Python trên cùng một máy tính.

Ví dụ, một máy tính có thể cần:
- Python 3.10 cho Project A.
- Python 3.11 cho Project B.
- Python 3.12 cho Project C.

pyenv giúp người dùng cài đặt, lựa chọn và chuyển đổi giữa các phiên bản Python.

Một số lệnh phổ biến:

```bash
pyenv versions
pyenv install 3.11.0
pyenv global 3.11.0
pyenv local 3.10.0
```

Lưu ý: Các lệnh trên minh họa cách sử dụng pyenv; việc cài đặt và hỗ trợ trên Windows có thể khác nhau, thường sử dụng pyenv-win.

#### d. Conda

Conda là công cụ quản lý package và môi trường, hỗ trợ Python cũng như nhiều ngôn ngữ và thư viện khoa học khác.

Conda thường được sử dụng trong khoa học dữ liệu, Machine Learning và AI.

Một số lệnh phổ biến:

Tạo môi trường:

```bash
conda create -n myenv python=3.11
```

Kích hoạt:

```bash
conda activate myenv
```

Cài đặt NumPy:

```bash
conda install numpy
```

Liệt kê các môi trường:

```bash
conda env list
```

Xóa môi trường:

```bash
conda env remove -n myenv
```

#### e. uv

`uv` là công cụ quản lý Python project và dependencies, được phát triển bởi Astral.

uv hỗ trợ tạo môi trường ảo, quản lý dependencies, khóa phiên bản thư viện và quản lý các phiên bản Python.

Một số lệnh phổ biến:

Khởi tạo dự án:

```bash
uv init my-project
```

Tạo môi trường ảo:

```bash
uv venv
```

Cài đặt thư viện:

```bash
uv add numpy
```

Chạy chương trình:

```bash
uv run main.py
```

Đồng bộ dependencies:

```bash
uv sync
```

### 1.4. So sánh các công cụ

| Công cụ | Chức năng chính |
|---|---|
| venv | Tạo môi trường ảo Python |
| virtualenv | Tạo và quản lý môi trường ảo |
| pyenv | Quản lý phiên bản Python |
| Conda | Quản lý môi trường và package |
| uv | Quản lý project, dependencies, môi trường và phiên bản Python |

Các công cụ này có thể bổ trợ cho nhau tùy theo nhu cầu của dự án.

---

## 2. VIRTUAL MACHINE (MÁY ẢO)

### 2.1. Virtual Machine là gì?

Virtual Machine (VM), hay máy ảo, là một máy tính được mô phỏng bằng phần mềm, có khả năng hoạt động tương tự một máy tính vật lý.

Máy ảo có thể có CPU ảo, RAM ảo, ổ cứng ảo, thiết bị mạng ảo và hệ điều hành riêng.

Nhờ công nghệ ảo hóa, người dùng có thể chạy nhiều hệ điều hành khác nhau trên cùng một máy tính vật lý.

Ví dụ: Một máy tính sử dụng Windows 10 có thể tạo một máy ảo chạy Ubuntu Linux.

### 2.2. Nguyên lý hoạt động

Máy ảo hoạt động thông qua một lớp phần mềm gọi là Hypervisor.

Các thành phần chính:

- Host Machine: Máy tính vật lý.
- Host OS: Hệ điều hành trên máy tính vật lý.
- Hypervisor: Phần mềm quản lý và tạo máy ảo.
- Guest OS: Hệ điều hành được cài đặt bên trong máy ảo.
- Virtual Hardware: Các tài nguyên phần cứng được mô phỏng như CPU, RAM, ổ cứng và card mạng.

Hypervisor phân bổ tài nguyên của máy tính vật lý cho các máy ảo, cho phép chúng hoạt động tương đối độc lập với nhau.

### 2.3. Các loại Hypervisor

**Type 1 – Bare-metal Hypervisor**

Hypervisor chạy trực tiếp trên phần cứng vật lý, không cần một hệ điều hành chủ thông thường ở bên dưới.

Đặc điểm:
- Hiệu năng và khả năng quản lý tài nguyên tốt.
- Thường được sử dụng trong trung tâm dữ liệu và hệ thống máy chủ.
- Phù hợp với môi trường doanh nghiệp.

Ví dụ: VMware ESXi, Microsoft Hyper-V.

**Type 2 – Hosted Hypervisor**

Hypervisor chạy như một ứng dụng bên trong hệ điều hành của máy tính vật lý.

Đặc điểm:
- Dễ cài đặt và sử dụng.
- Phù hợp cho học tập, nghiên cứu và thử nghiệm.
- Có thêm lớp hệ điều hành chủ nên thường có chi phí tài nguyên cao hơn Type 1.

Ví dụ: Oracle VirtualBox, VMware Workstation.

### 2.4. Ưu điểm và nhược điểm

**Ưu điểm:**
- Có thể chạy nhiều hệ điều hành trên một máy tính.
- Tận dụng hiệu quả tài nguyên phần cứng.
- Tạo môi trường thử nghiệm độc lập.
- Có thể sao lưu và khôi phục trạng thái máy ảo thông qua Snapshot.
- Hỗ trợ kiểm thử phần mềm và nghiên cứu hệ điều hành.

**Nhược điểm:**
- Tiêu tốn RAM, CPU và dung lượng ổ cứng.
- Hiệu năng có thể thấp hơn máy tính vật lý.
- Cần cấu hình tài nguyên phù hợp.
- Có thể gặp vấn đề tương thích với một số thiết bị hoặc công nghệ ảo hóa.

### 2.5. Ứng dụng của Virtual Machine

- Chạy nhiều hệ điều hành trên cùng một máy tính.
- Kiểm thử phần mềm trong các môi trường khác nhau.
- Học tập và nghiên cứu hệ điều hành.
- Triển khai máy chủ.
- Thử nghiệm phần mềm mà không ảnh hưởng trực tiếp đến hệ điều hành chính.

### 2.6. Một số phần mềm máy ảo phổ biến

- Oracle VirtualBox.
- VMware Workstation.
- Microsoft Hyper-V.
- VMware ESXi.

---

## 3. DOCKER CONTAINER

### 3.1. Container là gì?

Container là một phương pháp ảo hóa ở mức hệ điều hành, cho phép đóng gói ứng dụng cùng với các thư viện và dependencies cần thiết để ứng dụng có thể chạy trong một môi trường nhất quán.

Khác với Virtual Machine, container thông thường không cần chạy một hệ điều hành Guest riêng biệt. Các container chia sẻ kernel của hệ điều hành host trong cùng một môi trường container.

Nhờ vậy, container thường nhẹ hơn và có thời gian khởi động nhanh hơn máy ảo.

### 3.2. Docker là gì?

Docker là một nền tảng hỗ trợ xây dựng, phân phối và chạy ứng dụng trong container.

Docker giúp lập trình viên đóng gói ứng dụng cùng các thành phần phụ thuộc vào một môi trường thống nhất.

Nhờ Docker, ứng dụng có thể hoạt động nhất quán hơn giữa máy tính cá nhân, máy chủ và môi trường triển khai.

### 3.3. Kiến trúc Docker

Các thành phần chính:

**Docker Client**

Là công cụ giao tiếp giữa người dùng và Docker Engine thông qua các lệnh Docker.

Ví dụ:

```bash
docker run
docker build
docker pull
```

**Docker Daemon (dockerd)**

Là tiến trình nền chịu trách nhiệm quản lý Docker objects như images, containers và networks.

**Docker Image**

Là một mẫu đóng gói chỉ đọc, chứa ứng dụng và các thành phần cần thiết để tạo container.

**Docker Container**

Là một instance đang chạy hoặc được tạo ra từ Docker Image. Container cung cấp môi trường thực thi cho ứng dụng.

**Docker Registry**

Là nơi lưu trữ và phân phối Docker Images.

Ví dụ: Docker Hub.

### 3.4. Dockerfile là gì?

Dockerfile là một tệp văn bản chứa các chỉ dẫn để xây dựng Docker Image.

Ví dụ Dockerfile cho ứng dụng Python:

```dockerfile
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD ["python", "main.py"]
```

Ý nghĩa:

- FROM: Chọn image nền.
- WORKDIR: Thiết lập thư mục làm việc.
- COPY: Sao chép tệp vào image.
- RUN: Thực thi lệnh trong quá trình xây dựng image.
- CMD: Xác định lệnh mặc định khi container được chạy.

### 3.5. Một số lệnh Docker cơ bản

Kiểm tra phiên bản:

```bash
docker --version
```

Tải image:

```bash
docker pull python:3.11-slim
```

Liệt kê image:

```bash
docker images
```

Chạy container:

```bash
docker run -it python:3.11-slim
```

Liệt kê container đang chạy:

```bash
docker ps
```

Liệt kê tất cả container:

```bash
docker ps -a
```

Dừng container:

```bash
docker stop <container_id>
```

Xóa container:

```bash
docker rm <container_id>
```

### 3.6. Ưu điểm và nhược điểm

**Ưu điểm:**
- Nhẹ hơn máy ảo trong nhiều trường hợp.
- Khởi động nhanh.
- Dễ dàng đóng gói và phân phối ứng dụng.
- Hạn chế vấn đề khác biệt môi trường khi triển khai.
- Hỗ trợ mở rộng và triển khai nhiều dịch vụ.

**Nhược điểm:**
- Không cung cấp hệ điều hành riêng cho mỗi container.
- Có thể phát sinh vấn đề bảo mật nếu cấu hình không đúng.
- Cần kiến thức về image, network, volume và container lifecycle.
- Quản lý hệ thống container phức tạp có thể cần thêm công cụ như Kubernetes.

### 3.7. Ứng dụng của Docker Container

- Đóng gói ứng dụng.
- Triển khai ứng dụng trên máy chủ.
- Xây dựng môi trường phát triển thống nhất.
- Hỗ trợ CI/CD.
- Triển khai kiến trúc Microservices.
- Kiểm thử ứng dụng trong môi trường cô lập.

---

## 4. GIT AND GITHUB

### 4.1. Git là gì?

Git là một hệ thống quản lý phiên bản phân tán (Distributed Version Control System – DVCS).

Git cho phép theo dõi những thay đổi của mã nguồn và các tệp trong dự án theo thời gian.

Nhờ Git, người dùng có thể:
- Theo dõi lịch sử thay đổi.
- Khôi phục phiên bản trước đó.
- Làm việc trên các nhánh khác nhau.
- Kết hợp công việc của nhiều người.
- Quản lý quá trình phát triển phần mềm.

### 4.2. GitHub là gì?

GitHub là một nền tảng lưu trữ và cộng tác phát triển phần mềm dựa trên Git.

Git và GitHub không phải là một.

- Git là công cụ quản lý phiên bản.
- GitHub là nền tảng trực tuyến hỗ trợ lưu trữ repository Git và cộng tác.

Git có thể hoạt động trên máy tính cá nhân mà không cần kết nối Internet. GitHub giúp lưu trữ và chia sẻ repository trực tuyến.

### 4.3. Một số khái niệm quan trọng

**Repository (Repo)**

Là kho lưu trữ dự án, chứa mã nguồn, tài liệu và lịch sử thay đổi.

**Commit**

Là một bản ghi lưu lại những thay đổi đã được đưa vào lịch sử Git.

**Branch**

Là một nhánh phát triển độc lập, cho phép thực hiện thay đổi mà không ảnh hưởng trực tiếp đến nhánh khác.

**Clone**

Là thao tác sao chép một repository từ máy chủ về máy tính cá nhân.

**Push**

Là thao tác đưa các commit từ repository cục bộ lên repository từ xa.

**Pull**

Là thao tác lấy và tích hợp các thay đổi từ repository từ xa vào repository cục bộ.

**Merge**

Là thao tác kết hợp các thay đổi từ các nhánh khác nhau.

### 4.4. Quy trình làm việc cơ bản với Git

Một quy trình phổ biến:

1. Tạo hoặc mở repository.
2. Thực hiện thay đổi các tệp.
3. Kiểm tra những thay đổi bằng git status.
4. Đưa các tệp vào staging area bằng git add.
5. Tạo commit bằng git commit.
6. Đẩy commit lên GitHub bằng git push.

Một số lệnh cơ bản:

Kiểm tra trạng thái:

```bash
git status
```

Thêm tất cả thay đổi:

```bash
git add .
```

Tạo commit:

```bash
git commit -m "Update project"
```

Đẩy lên GitHub:

```bash
git push
```

Lấy thay đổi mới:

```bash
git pull
```

Xem lịch sử commit:

```bash
git log --oneline
```

### 4.5. GitHub Repository và cách nộp bài

GitHub Repository là nơi lưu trữ dự án trực tuyến.

Để nộp bài tập, sinh viên có thể:

1. Tạo tài khoản GitHub.
2. Tạo repository cho bài tập.
3. Kết nối thư mục dự án trên máy tính với repository.
4. Đưa mã nguồn và tài liệu vào repository.
5. Sử dụng Git để commit và push các thay đổi.
6. Kiểm tra repository trên GitHub.
7. Gửi đường dẫn repository cho giảng viên.

### 4.6. Vai trò của README.md

README.md là tệp tài liệu được sử dụng để giới thiệu repository.

Một README.md tốt nên có:
- Tên và giới thiệu dự án.
- Mục tiêu bài tập.
- Nội dung thực hiện.
- Cấu trúc thư mục.
- Hướng dẫn cài đặt và chạy demo.
- Kết quả thực hành.
- Tài liệu tham khảo (nếu có).

GitHub tự động hiển thị nội dung README.md trên trang chính của repository, giúp người xem dễ dàng hiểu dự án.

---

## 5. COMPARISON: VIRTUAL ENVIRONMENT, VIRTUAL MACHINE AND CONTAINER

Đây là ba công nghệ có mục đích khác nhau nhưng đều hỗ trợ tạo môi trường làm việc độc lập.

| Tiêu chí | Virtual Environment | Virtual Machine | Container |
|---|---|---|---|
| Mức độ ảo hóa | Python environment | Phần cứng | Hệ điều hành |
| Hệ điều hành riêng | Không | Có | Thường không |
| Kernel riêng | Không | Có (Guest OS) | Không, chia sẻ kernel host |
| Tài nguyên sử dụng | Thấp | Cao hơn | Thường thấp |
| Thời gian khởi động | Nhanh | Thường chậm hơn | Nhanh |
| Mục đích | Quản lý thư viện Python | Mô phỏng máy tính | Đóng gói ứng dụng |

### Kết luận

Virtual Environment, Virtual Machine và Container đều giúp tạo ra những môi trường làm việc độc lập nhưng giải quyết các vấn đề khác nhau.

- Virtual Environment phù hợp để quản lý thư viện và dependencies của dự án Python.
- Virtual Machine phù hợp để chạy một hệ điều hành hoàn chỉnh trong môi trường ảo.
- Docker Container phù hợp để đóng gói, phân phối và triển khai ứng dụng một cách nhất quán.

Trong phát triển phần mềm hiện đại, các công nghệ này có thể được kết hợp để xây dựng môi trường phát triển và triển khai ứng dụng hiệu quả.

---

## 6. CONCLUSION

Thông qua việc tìm hiểu Python Environment Management, Virtual Machine, Docker Container và Git/GitHub, có thể thấy rằng việc quản lý môi trường phát triển và mã nguồn đóng vai trò quan trọng trong quá trình xây dựng phần mềm.

Các kiến thức này là nền tảng cần thiết để phát triển những dự án Python, Machine Learning và các ứng dụng phần mềm trong tương lai.
