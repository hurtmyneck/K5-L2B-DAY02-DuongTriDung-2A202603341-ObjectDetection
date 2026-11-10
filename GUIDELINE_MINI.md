# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp     | Định nghĩa của bạn         | Ví dụ/điểm phân biệt                |
| ------- | -------------------------- | ----------------------------------- |
| `car`   | xe ô tô con, xe suv        | xe có đầu và đuôi thấp hơn nóc xe   |
| `truck` | xe tải                     | xe có thùng hàng                    |
| `bus`   | xe buýt                    | xe cao, dài                         |
| `van`   | xe van chở người hoặc hàng | xe có đuôi hình hộp liền với đầu xe |

## Quy tắc chung

- Box bám sát vật thể nghĩa là: box phải bao vừa đủ toàn bộ phần nhìn thấy của vật thể, hạn chế chứa vùng nền thừa và không cắt mất các bộ phận có thể nhìn thấy
- Vật thể bị che khuất: vẽ bounding box quanh phần vật thể thực sự nhìn thấy, không tự suy đoán phần bị che khuất
- Vật thể bị cắt bởi rìa ảnh: gán nhãn phần vật thể nằm trong khung hình
- Vật thể rất nhỏ/mơ hồ: gán nhãn khi có thể nhận diện tương đối chắc chắn loại vật thể

## Ghi lại quyết định cho ít nhất ba ca mơ hồ

| Ảnh             | Tình huống                                             | Quyết định cuối         | Lý do theo schema                          |
| --------------- | ------------------------------------------------------ | ----------------------- | ------------------------------------------ |
| `drive_006.jpg` | xe ô tô trắng có hình dạng giống xe van                | gán là car              | kích thước không phù hợp với xe van        |
| `drive_021.jpg` | xe bị che khuất                                        | gán là car              | vẫn đủ rõ ràng để nhận dạng                |
| `drive_030.jpg` | có quá nhiều xe có kích thước trên ảnh quá nhỏ, quá mờ | không gán các xe quá xa | kích thước xe quá nhỏ để nhận diện loại xe |
