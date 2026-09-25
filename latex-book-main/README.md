## Pet Health Care – Hệ thống Chăm sóc Sức khỏe Thú cưng

Repository này chứa mã nguồn SQL và tài liệu báo cáo cho đề tài Hệ thống Chăm sóc Sức khỏe Thú cưng. Đề tài tập trung vào việc phân tích, thiết kế và xây dựng cơ sở dữ liệu phục vụ quản lý thông tin khách hàng, thú cưng, bác sĩ thú y, nhân viên, lịch hẹn, hồ sơ khám bệnh, hóa đơn và phòng chăm sóc.

## Mục tiêu

Cơ sở dữ liệu được xây dựng nhằm:

+ Quản lý thông tin khách hàng và thú cưng.
+ Quản lý thông tin bác sĩ thú y, nhân viên và tài khoản quản trị.
+ Quản lý lịch hẹn khám giữa khách hàng, thú cưng và bác sĩ thú y.
+ Lưu trữ hồ sơ khám bệnh và thông tin điều trị.
+ Quản lý hóa đơn và trạng thái thanh toán.
+ Quản lý thông tin phòng chăm sóc.
+ Đảm bảo tính toàn vẹn và nhất quán của dữ liệu thông qua khóa chính, khóa ngoại và các ràng buộc dữ liệu.

## Cấu trúc hệ thống

Cơ sở dữ liệu gồm 9 bảng chính:

+ `Customer` – Thông tin khách hàng.
+ `Pet` – Thông tin thú cưng.
+ `Veterinarian` – Thông tin bác sĩ thú y.
+ `Staff` – Thông tin nhân viên.
+ `Admin` – Thông tin tài khoản quản trị.
+ `Booking` – Thông tin lịch hẹn khám.
+ `Invoice` – Thông tin hóa đơn.
+ `MedicalRecord` – Hồ sơ khám bệnh.
+ `Room` – Thông tin phòng chăm sóc.

Các mối quan hệ chính:

+ Một khách hàng có thể sở hữu nhiều thú cưng.
+ Một khách hàng có thể có nhiều lịch hẹn.
+ Một thú cưng có thể có nhiều lịch hẹn và hồ sơ khám bệnh.
+ Một bác sĩ thú y có thể thực hiện nhiều lịch hẹn và hồ sơ khám bệnh.
+ Một nhân viên có thể hỗ trợ nhiều lịch hẹn.
+ Một lịch hẹn có tối đa một hóa đơn.


## Công nghệ sử dụng

+ Database: MySQL
+ Query language: SQL
+ Documentation: LaTeX
+ Diagram: ERD
+ LaTeX compiler: pdfLaTeX
+ Bibliography: BibTeX

## Cài đặt cơ sở dữ liệu

Tạo cơ sở dữ liệu:

CREATE DATABASE pet_health_care;
USE pet_health_care;


Sau đó thực hiện các câu lệnh `CREATE TABLE` theo thứ tự từ các bảng cha đến các bảng có khóa ngoại.

Tiếp theo, thực hiện các câu lệnh `INSERT` để thêm dữ liệu mẫu.

## Biên dịch báo cáo LaTeX

Mở file:
book.tex và biên dịch bằng pdfLaTeX.


## Mô hình ERD

Mô hình ERD của hệ thống được lưu tại:
figures/pet_health_care_erd.pdf


Mô hình thể hiện các thực thể, thuộc tính, khóa chính, khóa ngoại và các mối quan hệ giữa các bảng trong hệ thống.

## Chuẩn hóa cơ sở dữ liệu

Cơ sở dữ liệu được phân tích và chuẩn hóa nhằm giảm dư thừa dữ liệu và hạn chế các bất thường khi thêm, sửa hoặc xóa dữ liệu.

Các bảng được thiết kế hướng đến dạng chuẩn 3NF (Third Normal Form).

Đặc biệt, bảng `Invoice` không lưu trực tiếp `customer_id` vì thông tin khách hàng có thể được xác định thông qua quan hệ:

Invoice → Booking → Customer


Việc loại bỏ thuộc tính dư thừa giúp hạn chế khả năng xảy ra mâu thuẫn dữ liệu.

## Kiểm thử

Các chức năng và ràng buộc cơ bản được kiểm tra thông qua các truy vấn SQL, bao gồm:

+ Kiểm tra khóa chính.
+ Kiểm tra khóa ngoại.
+ Kiểm tra giá trị `NULL`.
+ Kiểm tra ràng buộc `UNIQUE`.
+ Kiểm tra quan hệ giữa các bảng.
+ Kiểm tra cập nhật dữ liệu.
+ Kiểm tra xóa dữ liệu.
+ Kiểm tra các truy vấn thống kê.

## Tài liệu tham khảo

Các tài liệu sử dụng trong quá trình thực hiện đề tài được lưu trong file:
book.bib và được sử dụng trong báo cáo LaTeX thông qua BibTeX.
