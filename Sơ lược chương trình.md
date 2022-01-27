Tóm lược:
- Dữ liệu của mình được lấy từ 3 nguồn là virusshare, drebin, cicdataset.
- Flow sẽ là từ app android, sẽ gửi 1 file apk lên server, server trích tách dữ liệu, và trả về kết quả, app android nhận kết quả và render nội dung lên màn hình.
- Cách máy học: semi supervised learning, inductive learning, self learning.
- Phân loại nhiều loại mã độc. Chúng ta cần phân biệt được các loại malware, virus khác nhau để nghiên cứu cách từng loại lây lan, gây hại như thế nào, để rồi từ đó tìm ra cách để đoán nhận, ngăn chặn và phòng chống xâm nhập.

Các bước chuẩn bị:
- Máy cần có bộ dịch ngược apktool, dịch ra để thu đc mã hợp ngữ android.
- Trích xuất ra các api mà ứng dụng sử dụng.
- Xây dựng lên các ma trận độ đo tương đồng và tạo nên các feature vector.
- Có feature rồi sẽ đưa vào mô hình học máy đoán nhận.

Lưu ý:
- Chạy nhiều epoch (Việc train nhiều epoch nó sẽ khiến cho cái độ chính xác của học máy cao hơn).
- Không đếm số lần api lặp lại, mà sẽ đếm là 1 api có bao nhiêu app sử dụng.
- Lưu api bên benign sử dụng và api bên malware sử dụng riêng, để tiện theo dõi.
- lấy top250benign và top250malware trộn lại cho đủ 500 rồi sử dụng nó trong avgsim lấy được 16 ma trận ứng với 16 metapath.
- Phân loại dùng multiclass K neighbor.
