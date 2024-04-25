# Install SUI from binaries

## 1. Ưu và nhược

  Ưu điểm: 
- Nhanh rất nhiều so với việc cài sui bằng cargo. Máy mình luôn tốn hơn 30 phút cho việc cài sui = cargo.
- Dễ dàng kiểm soát version

Nhược điểm (cũng không hoàn toàn là nhược điểm tại vì có cách khắc phục)
- Không thể xài global => khai báo environment variable
- Các service riêng lẻ từng file => chạy từng file cũng không ảnh hưởng mấy

## 2. Hướng dẫn cài đặt

### Bước 1: Tải SUI binaries

Truy cập vào đường link sau đây [Releases · MystenLabs/sui (github.com)](https://github.com/MystenLabs/sui/releases) và tải sui version mong muốn.

Trong hướng dẫn này, mình sẽ cài [Release testnet-v1.18.1 · MystenLabs/sui (github.com)](https://github.com/MystenLabs/sui/releases/tag/testnet-v1.18.1)

### Bước 2: Đưa file zip từ Windows vào WSL

Ở terminal WSL, bạn gõ lệnh `explorer.exe .`. Lúc này File Explorer sẽ hiện lên với vị trí là working directory hiện tại của bạn ở WSL. Sau đó chỉ đơn giản là bạn copy file sang. 

### Bước 3: Giải nén

Sau khi có được file zip ở bước 2, bạn tiến hành giải nén `tar -xzvf <filename>.tgz`.

Sau khi giải nén xong, bạn sẽ có được 2 folder như trong hình dưới đây
![after extracting sui file zip](https://github.com/orgs/Weminal-labs/projects/6/assets/87592549/5ad6fa67-874f-4600-b26e-b5e2413f9ede)

Bạn chỉ cần quan tâm folder target thôi nhé.

![target/release](https://github.com/orgs/Weminal-labs/projects/6/assets/87592549/6f9db2c8-5bd6-433f-a132-d0d65287be63)

Đây là các file sui binary. Bạn chỉ cần quan tâm 2 file chính là: **sui-ubuntu-x86_64** và **sui-tool-ubuntu-x86_64**.

### Bước 4: Sử dụng

Để chạy các file binary này, bạn chỉ cần gõ lệnh `./<binary_filename>`.

![sui command](https://github.com/orgs/Weminal-labs/projects/6/assets/87592549/9fbf3de1-2d59-4f83-aac5-af5ea1aa2a0f)

Như vậy là ta đã cài đặt xong SUI từ binaries rồi nhé. Từ giờ muốn update SUI version thì bạn cài bằng cách này cho nhanh nhé chứ cài bằng cargo nó hơi khoai đợi hơn 30p mà cài còn bị lỗi :))). 

Tuy nhiên, đối với cách này chẳng lẽ mỗi lần muốn sử dụng SUI CLI là ta phải di chuyển vào thư mục trên mới chạy được. Bước tiếp theo mình sẽ hướng dẫn set environment variable.

### Bước 5: Cài đặt biến môi trường (optional)

Ở thư mục user hiện tại (~), bạn truy cập vào file **.bashrc** bằng nano, vim hoặc VS Code cũng được. 

Mình sẽ sử dụng vim nhé: `vim .bashrc`

Và thêm dòng này vào cuối file `export SUI_TESTNET_HOME="<absolute_path>/target/release"`

Sau khi save file, bạn gõ lệnh `source ~/.profile` để lưu thay đổi.

![SUI environment variable](https://github.com/orgs/Weminal-labs/projects/6/assets/87592549/323d001b-2ac6-4f1c-9b50-00c1c069bb2f)

![SUI environment variable + command](https://github.com/orgs/Weminal-labs/projects/6/assets/87592549/0ccf0417-bcd6-43f4-add0-0c588bb21368)

## 3. References
- [Install Sui | Sui Documentation](https://docs.sui.io/guides/developer/getting-started/sui-install#install-binaries)