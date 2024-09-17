# VIETNAMES

## crack elasticsearch cho docker

Crack elaticsearch 7.x/8.x bằng docker

Một srcipt tự động để Crack elaticsearch 7.x /8.x, có thể tự động biên dịch và tạo các bản vá bẻ khóa trong docker

Đã thử nghiệm phiên bản có thể biên dịch được

* elasticsearch 7.17.2

Đã thử nghiệm phiên bản cài đặt tự động

* elasticsearch 8.2.0
* elasticsearch 8.8.1
* elasticsearch 8.9.1
* elasticsearch 8.10.1
* elasticsearch 8.11.1
* elasticsearch 8.12.1

Xác minh nhập chứng chỉ phiên bản doanh nghiệp

* elasticsearch 8.12.2

**Không thể xác minh tính ổn định và tính khả dụng sau khi nhập chứng chỉ phiên bản doanh nghiệp**

### Cách sử dụng

Get srcipt

Lấy mã nguồn srcipt

```shell
git clone https://github.com/bibo318/crack-elasticsearch.git
```

Chạy srcipt với phiên bản

Chạy srcipt và chỉ định phiên bản đầy đủ (ví dụ: 8.2.0)

```shell
cd crack-elasticsearch
version=8.2.0
sudo bash crack.sh $version
```

Nhận bản crack x-pack-core-$version.jar

Các sản phẩm biên dịch và phần mềm trung gian biên dịch được lưu trong tại thư mục

```shell
# Local installation
cp output/x-pack-core-$version.crack.jar /usr/share/elasticsearch/modules/x-pack-core/x-pack-core-$version.jar

# Docker installation
-v output/x-pack-core-$version.crack.jar:/usr/share/elasticsearch/modules/x-pack-core/x-pack-core-$version.jar
```

### Crack và cài đặt

Bạn có thể trực tiếp hoàn thành phiên bản bẻ khóa và cài đặt Docker được chỉ định (single node) thông qua các srcipt

Người dùng có thể điều chỉnh các thông số theo nhu cầu riêng của mình và srcipt này chỉ mang tính chất tham khảo.

```
git clone https://github.com/bibo318/crack-elasticsearch.git
cd crack-elasticsearch-by-docker
version=8.2.0
sudo bash crack_and_install.sh $version
```

### Giấy phép Platinum

Trước hết, bạn cần đăng ký chứng chỉ cơ bản miễn phí trên trang web chính thức và tải xuống.

https://register.elastic.co/

Sau đó, sửa đổi các trường trong chứng chỉ thành như sau (thời gian có thể được sửa đổi nếu cần)

```
type = "platinum"
max_nodes = 1000
expiry_date_in_millis = "2147482800000"
```

Lưu file, sau đó tải file đã sửa đổi lên qua Kibana và hoàn tất kích hoạt thông qua nhập chứng chỉ Giấy phép.

### Others

Bạn có thể thay đổi shell `crack.sh` bằng url http_proxy /https_proxy
Bạn có thể sửa đổi `crack.sh` để sử dụng proxy truy cập mạng nhằm tránh lỗi truy cập mạng

```shell
docker build --no-cache -f Dockerfile \
  --build-arg VERSION="${version}" \
  --build-arg HTTP_PROXY="http://1.2.3.4:8080" \
  --build-arg HTTPS_PROXY="http://1.2.3.4:8080" \
  --tag ${service_name}:${version} .

docker run -it --rm \
  -v $(pwd)/output:/crack/output \
  -e HTTP_PROXY="http://1.2.3.4:8080" \
  -e HTTPS_PROXY="http://1.2.3.4:8080" \
  ${service_name}:${version}
```

################################################

# ENGLISH

## crack elasticsearch for docker

Crack elasticsearch 7.x/8.x with docker

An automatic srcipt to Crack elasticsearch 7.x /8.x, which can automatically compile and generate crack patches in docker

Tested the compilable version
*elasticsearch 7.17.2

Tested automatic installation version
*elasticsearch 8.2.0
*elasticsearch 8.8.1
*elasticsearch 8.9.1
*elasticsearch 8.10.1
*elasticsearch 8.11.1
*elasticsearch 8.12.1

Verify enterprise edition certificate import
*elasticsearch 8.12.2

**Unable to verify stability and availability after importing enterprise edition certificate**

### How to use

Get script

Get the srcipt source code

```shell
git clone https://github.com/bibo318/crack-elasticsearch.git
```

Run srcipt with version

Run srcipt and specify the full version (e.g. 8.2.0)

```shell
cd crack-elasticsearch
version=8.2.0
sudo bash crack.sh $version
```

Get the x-pack-core-$version.jar crack
Compilation products and compilation middleware are stored in the directory

```shell
# Local installation
cp output/x-pack-core-$version.crack.jar /usr/share/elasticsearch/modules/x-pack-core/x-pack-core-$version.jar

# Docker installation
-v output/x-pack-core-$version.crack.jar:/usr/share/elasticsearch/modules/x-pack-core/x-pack-core-$version.jar
```

### Crack and install

You can directly complete the jailbreak version and install the specified Docker (single node) through the srcipts

Users can adjust the parameters according to their own needs and this srcipt is for reference only.

```
git clone https://github.com/bibo318/crack-elasticsearch.git
cd crack-elasticsearch-by-docker
version=8.2.0
sudo bash crack_and_install.sh $version
```

### Platinum License

First of all, you need to register for a free basic certificate on the official website and download it.

https://register.elastic.co/

Then modify the fields in the certificate to the following (time can be modified if needed)

```
type = "platinum"
max_nodes = 1000
expiry_date_in_millis = "2147482800000"
```

Save the file, then upload the modified file via Kibana and complete activation via importing the License certificate.

### Others

You can change the `crack.sh` shell with the url http_proxy /https_proxy
You can modify `crack.sh` to use a network access proxy to avoid network access errors

```shell
docker build --no-cache -f Dockerfile\
  --build-arg VERSION="${version}" \
  --build-arg HTTP_PROXY="http://1.2.3.4:8080" \
  --build-arg HTTPS_PROXY="http://1.2.3.4:8080" \
  --tag ${service_name}:${version} .

docker run -it --rm \
  -v $(pwd)/output:/crack/output \
  -e HTTP_PROXY="http://1.2.3.4:8080" \
  -e HTTPS_PROXY="http://1.2.3.4:8080" \
  ${service_name}:${version}
```
