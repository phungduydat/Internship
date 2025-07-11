Project Proposal Guidelines - FCJ Internship


Continuous Monitoring và Alerting trong DevOps



Executive Summary


Dự án này tập trung vào việc triển khai một Hệ thống giám sát và cảnh báo liên tục (Continuous Monitoring & Alerting) toàn diện cho nền tảng học tiếng Anh trực tuyến WebEnglish, được xây dựng trên nền tảng AWS. Mục tiêu chính là nâng cao khả năng phát hiện, xử lý và khắc phục sự cố vận hành một cách tự động và hiệu quả, đảm bảo độ ổn định và hiệu suất cao cho hệ thống trong môi trường DevOps năng động.


Problem statement


Hiện tại, nền tảng học tiếng Anh trực tuyến WebEnglish đang đối mặt với nhiều thách thức đáng kể trong việc quản lý và vận hành hệ thống. Các phương pháp giám sát truyền thống đã bộc lộ nhiều hạn chế, không theo kịp quy mô và tốc độ phát triển nhanh chóng của hệ thống, dẫn đến những hậu quả nghiêm trọng:


Downtime kéo dài: Các sự cố vận hành thường không được phát hiện kịp thời, gây ra thời gian gián đoạn dịch vụ kéo dài, ảnh hưởng trực tiếp đến trải nghiệm người dùng và uy tín của WebEnglish.


Phản hồi chậm với lỗi nghiêm trọng: Việc thiếu khả năng giám sát sâu sát các thành phần backend hoặc cơ sở dữ liệu khiến thời gian phản hồi và khắc phục các lỗi quan trọng bị kéo dài, tiềm ẩn rủi ro lớn về mất dữ liệu và hiệu suất.


Thiếu báo cáo trực quan: Lãnh đạo và đội ngũ DevOps thiếu các báo cáo tổng quan và trực quan về tình trạng hệ thống, gây khó khăn trong việc đưa ra quyết định chiến lược và tối ưu hóa vận hành.


Trong bối cảnh WebEnglish hoạt động theo mô hình DevOps, việc thiếu một hệ thống giám sát thông minh, chủ động và tích hợp chặt chẽ vào quy trình là một rủi ro lớn đối với độ ổn định và hiệu suất tổng thể của hệ thống. Điều này không chỉ ảnh hưởng đến khả năng mở rộng mà còn tác động trực tiếp đến sự hài lòng của người dùng và lợi thế cạnh tranh của WebEnglish.


Solution overview 


Hệ thống Giám sát & Cảnh báo Thông minh (Intelligent Monitoring & Alerting System). Hệ thống này được thiết kế để tích hợp mượt mà vào quy trình DevOps hiện có của WebEnglish. Về mặt kiến trúc, hệ thống sẽ được triển khai hoàn toàn trên nền tảng AWS, tận dụng các dịch vụ đám mây mạnh mẽ để đảm bảo khả năng mở rộng, độ tin cậy và tối ưu chi phí.


Các Tính năng Chính (Key Features)


Triển khai Giám sát (Monitoring Implementation)


Thu thập và giám sát các chỉ số hiệu suất quan trọng từ nhiều nguồn khác nhau bao gồm:


Amazon ECS (Elastic Container Service): Giám sát tình trạng và hiệu suất của các container.


Amazon RDS (Relational Database Service): Giám sát hiệu suất và sức khỏe của cơ sở dữ liệu.


Ứng dụng Java Spring Boot: Giám sát hiệu suất ứng dụng thông qua các metrics và logs.


Sử dụng AWS CloudWatch làm công cụ thu thập, lưu trữ và trực quan hóa dữ liệu giám sát.


Tích hợp AWS X-Ray để theo dõi và phân tích các yêu cầu từ đầu đến cuối (end-to-end tracing), giúp xác định các điểm nghẽn và lỗi trong kiến trúc microservices.


Phát hiện Bất thường (Anomaly Detection):


Sử dụng CloudWatch Anomaly Detector để tự động học các mẫu hành vi bình thường của hệ thống và phát hiện các điểm bất thường theo thời gian thực mà không cần cài đặt ngưỡng cố định


Tích hợp AWS DevOps Guru để sử dụng máy học (Machine Learning) tự động xác định các hành vi bất thường, phát hiện các sự cố vận hành và đưa ra khuyến nghị khắc phục.


Phản hồi Tự động (Automated Response):


Thiết lập các quy tắc và hành động tự động để phản ứng ngay lập tức khi phát hiện sự cố.


Tự động kích hoạt AWS Lambda hoặc AWS Step Functions để thực hiện các hành động khắc phục, chẳng hạn như:


Mở rộng quy mô ECS service (tăng số lượng tác vụ hoặc instance) khi tải tăng đột biến.


Khởi động lại dịch vụ bị lỗi hoặc không phản hồi.


Gửi cảnh báo tức thì đến các kênh liên lạc phù hợp.


Quy trình Leo thang Cảnh báo (Escalation Procedures):


Xây dựng quy trình leo thang cảnh báo ba cấp độ để đảm bảo các sự cố nghiêm trọng được xử lý nhanh chóng và không bị bỏ sót:


Cấp độ 1: Thông báo tức thì qua Amazon SNS (Simple Notification Service) đến đội ngũ DevOps.


Cấp độ 2: Tích hợp với PagerDuty để đảm bảo thông báo được gửi đến đúng người phụ trách theo ca trực và có cơ chế theo dõi phản hồi.


Cấp độ 3: Thông báo đến Quản lý cấp cao nếu sự cố không được giải quyết trong khung thời gian quy định, đảm bảo mọi rủi ro lớn đều được nhận biết.


Bảng điều khiển & Tối ưu hóa Cảnh báo (Dashboard & Alert Tuning):


Xây dựng các dashboard trực quan và dễ hiểu với CloudWatch Dashboards và Amazon QuickSight, cung cấp cái nhìn tổng quan về tình trạng hệ thống cho cả đội ngũ kỹ thuật và lãnh đạo.


Liên tục tối ưu hóa các ngưỡng cảnh báo và quy tắc phát hiện để giảm thiểu false positives (cảnh báo sai) và false negatives (bỏ sót cảnh báo), đảm bảo đội ngũ chỉ nhận được những cảnh báo thực sự cần thiết.


Quy trình Vận hành & Tối ưu hóa (Operational Procedures & Optimization):


Thiết lập runbook (tài liệu hướng dẫn xử lý sự cố) chi tiết cho các kịch bản lỗi phổ biến.


Tận dụng CloudWatch Log Insights để phân tích log một cách hiệu quả, giúp nhanh chóng xác định nguyên nhân gốc rễ của vấn đề.


Triển khai auto-scaling cho các dịch vụ quan trọng để đảm bảo hệ thống luôn duy trì hiệu suất tối ưu và khả năng chịu tả


Business benefits và ROI summary


Business Benefits:


Giảm thời gian khắc phục sự cố: Hệ thống giám sát và cảnh báo thông minh giúp giảm đáng kể thời gian cần thiết để xác định, chẩn đoán và giải quyết các sự cố, từ hàng giờ xuống còn vài phút.


Phản ứng tức thời: Với các cảnh báo tự động và quy trình phản hồi được thiết lập, đội DevOps có thể phản ứng nhanh chóng với các vấn đề phát sinh, ngăn chặn chúng leo thang thành các sự cố lớn hơn.


Cải thiện độ ổn định hệ thống: Việc giám sát liên tục và phát hiện sớm các bất thường giúp duy trì sự ổn định của hệ thống, giảm thiểu thời gian ngừng hoạt động và đảm bảo trải nghiệm người dùng liền mạch. Điều này trực tiếp dẫn đến tăng mức độ hài lòng của người dùng.


Cho phép mở rộng hệ thống dễ dàng: Khả năng tự động mở rộng tài nguyên dựa trên tải hệ thống đảm bảo rằng ứng dụng có thể xử lý các đợt tăng lưu lượng truy cập mà không gặp phải vấn đề về hiệu suất, từ đó hỗ trợ tăng trưởng kinh doanh.


ROI Summary


Dự kiến hoàn vốn trong 6–9 tháng thông qua tiết kiệm chi phí downtime và nhân sự vận hành.


Chi phí AWS ước tính ~$1,500/tháng so với tổn thất do downtime lên đến hàng nghìn USD mỗi lần.


Giá trị đầu tư thấp so với lợi ích dài hạn về sự ổn định và hiệu quả hệ thống.


Investment Required & Timeline




|  |  |
| --- | --- |
| Thành phần | Thông tin
 |
| Chi phí hạ tầng AWS | Khoảng ~$1,500 USD/tháng (ước tính, bao gồm chi phí cho các dịch vụ ECS, CloudWatch, X-Ray, Lambda, QuickSight, v.v.). |
| Nhân sự triển khai
 | Cần sự tham gia của 1 DevOps Engineer và 1 Backend Developer để tích hợp và cấu hình hệ thống.
 |
| Thời gian thực hiện
 | 3 tuần, chia thành 3 giai đoạn chính:
Tuần 1: Thiết lập và cấu hình các dịch vụ AWS cơ bản.
Tuần 2: Triển khai tính năng cảnh báo và phản hồi tự động.
Tuần 3: Tối ưu hóa hệ thống, tinh chỉnh ngưỡng cảnh báo và thực hiện kiểm thử toàn diện.
 |


Success Metrics & Expected Outcomes




|  |  |
| --- | --- |
| Chỉ số Đo lường | Kết quả Kỳ vọng
 |
| Hệ số Uptime | Hệ số Uptime |
| > 99.9%, đảm bảo dịch vụ luôn sẵn sàng cho người dùng. | > 99.9%, đảm bảo dịch vụ luôn sẵn sàng cho người dùng. |
| Thời gian khắc phục trung bình (MTTR) | Thời gian khắc phục trung bình (MTTR) |
| < 15 phút, giúp giảm thiểu tối đa tác động của sự cố. | < 15 phút, giúp giảm thiểu tối đa tác động của sự cố. |
| Tỷ lệ cảnh báo chính xác (Precision) | Tỷ lệ cảnh báo chính xác (Precision) |


Problem Statement


Current situation analysis


WebEnglish đang là một nền tảng học tiếng Anh trực tuyến phát triển nhanh chóng, phục vụ hàng nghìn người dùng hàng ngày. Hệ thống backend của chúng ta được xây dựng trên môi trường onpremise.


Tuy nhiên, dù có nền tảng kiến trúc vững chắc, WebEnglish hiện vẫn thiếu một cơ chế giám sát và cảnh báo chủ động (proactive monitoring and alerting) trên dịch vụ aws . Điều này gây ra những thách thức đáng kể cho đội ngũ DevOps trong việc phát hiện, phân tích và xử lý các sự cố vận hành một cách kịp thời và hiệu quả, dẫn đến rủi ro về độ ổn định và trải nghiệm người dùng.


Pain points identification với quantified impact


Sự thiếu hụt hệ thống giám sát thông minh đang tạo ra những điểm đau rõ rệt, gây ra các tác động tiêu cực có thể định lượng được:




|  |  |
| --- | --- |
| Vấn đề Phát Sinh | Ảnh Hưởng Cụ Thể (Định Lượng)
 |
| Không phát hiện sớm lỗi hiệu năng | Dẫn đến tăng thời gian downtime trung bình (MTTD - Mean Time To Detect) từ 45–90 phút/lỗi, trực tiếp làm gián đoạn trải nghiệm người dùng và ảnh hưởng đến năng suất của đội ngũ vận hành. |
| Thiếu cơ chế cảnh báo bất thường chủ động | Các sự cố hệ thống thường chỉ được phát hiện khi có phản hồi từ người dùng cuối hoặc các báo cáo lỗi thủ công. Điều này làm tăng đáng kể MTTR (Mean Time To Recovery) và phản ánh sự thiếu chủ động trong quản lý rủi ro. |
| Không có cơ chế tự động phản ứng với sự cố | Mỗi sự cố phát sinh đều đòi hỏi sự can thiệp thủ công hoàn toàn từ đội ngũ DevOps. Quá trình này không chỉ tốn thời gian mà còn chậm trễ trong việc khôi phục dịch vụ, đặc biệt trong các kịch bản lỗi lặp lại hoặc lỗi nhỏ có thể tự động khắc phục. |
| Thiếu báo cáo tổng thể và trực quan về sức khỏe hệ thống | Ban lãnh đạo và quản lý cấp cao không có cái nhìn theo thời gian thực về tình trạng tổng quan của hệ thống. Điều này cản trở khả năng đánh giá sức khỏe nền tảng, đưa ra quyết định chiến lược nhanh chóng và tối ưu hóa tài nguyên. |


Stakeholders affected và their concerns


Việc thiếu hệ thống giám sát hiệu quả không chỉ ảnh hưởng đến vận hành mà còn tác động rộng khắp đến nhiều bộ phận và cá nhân quan trọng trong WebEnglish:




|  |  |
| --- | --- |
| Đối Tượng Liên Quan | Đối Tượng Liên Quan |
| Leader/Project Manager | Thiếu cái nhìn toàn cảnh về hiệu suất và rủi ro hệ thống, gây khó khăn trong việc đưa ra các quyết định chiến lược và phân bổ nguồn lực kỹ thuật một cách tối ưu. |
| Đội ngũ DevOps
 | Phải liên tục xử lý sự cố một cách thủ công và phản ứng bị động. Điều này làm giảm năng suất tổng thể, hạn chế khả năng tập trung vào phát triển tính năng mới và cải tiến sản phẩm. |
| Người dùng  | Trải nghiệm học tập không ổn định, gián đoạn do downtime hoặc hiệu suất kém, dẫn đến sự bất mãn, mất niềm tin vào sản phẩm và có nguy cơ chuyển sang các đối thủ cạnh tranh. |


Business consequences của inaction


Nếu WebEnglish không chủ động triển khai hệ thống giám sát và cảnh báo thông minh, các hậu quả nghiêm trọng sẽ tiếp diễn:


Downtime kéo dài: Gián đoạn dịch vụ thường xuyên gây tổn thất tài chính và ảnh hưởng tiêu cực đến uy tín thương hiệu trong lĩnh vực giáo dục trực tuyến.


DevOps quá tải: Đội ngũ kỹ thuật phải liên tục xử lý sự cố, giảm năng suất và trì hoãn việc phát triển sản phẩm mới.


Thiếu dữ liệu chiến lược: Ban lãnh đạo không có cái nhìn toàn cảnh để ra quyết định kịp thời, ảnh hưởng đến mở rộng và quản trị rủi ro.


Không đảm bảo SLA: Dễ dẫn đến mất hợp đồng hoặc bị phạt trong các thỏa thuận dịch vụ với khách hàng doanh nghiệp.


Market opportunity (nếu applicable)


Thị trường học tiếng Anh trực tuyến tại Việt Nam đang bùng nổ mạnh mẽ, với nhu cầu ngày càng tăng cao về một môi trường học tập nhanh chóng, đơn giản, dễ tiếp cận mọi lúc mọi nơi. WebEnglish đang đứng trước một cơ hội vàng để nắm bắt xu hướng này và trở thành người dẫn đầu.


Với việc khai thác tối đa hạ tầng đám mây mạnh mẽ của AWS, WebEnglish có được những lợi thế cạnh định vượt trội:Khả năng mở rộng linh hoạt,Độ tin cậy và sẵn sàng cao,Tối ưu hóa chi phí,Đổi mới nhanh chóng


 Solution Architecture 


High-level architecture diagram



AWS services selection với justification









|  |  |  |
| --- | --- | --- |
| Dịch vụ AWS | Vai trò | Lý do lựa chọn |
| Amazon EC2 | Chạy ứng dụng Spring Boot trong Docker | Linh hoạt, dễ kiểm soát môi trường, tích hợp với Docker Compose |
| Amazon CloudWatch | Thu thập logs và metrics từ EC2 | Dịch vụ giám sát mặc định của AWS, hỗ trợ cấu hình tuỳ biến và cảnh báo |
| AWS CloudWatch Agent | Đẩy log & metrics từ EC2 | Hỗ trợ giám sát chi tiết (CPU, Memory, Disk...) cho EC2 |
| AWS Lambda | Tự động phản hồi khi cảnh báo xảy ra | Serverless, chi phí thấp, phản ứng gần như tức thời |
| Amazon SNS | Gửi thông báo cảnh báo | Tích hợp email, SMS, hoặc webhook |
| AWS DevOps Guru | Phát hiện bất thường bằng AI | Sử dụng ML để phân tích hành vi ứng dụng và cảnh báo thông minh |
| AWS X-Ray | Tracing request và phân tích lỗi | Phân tích hiệu năng từ đầu đến cuối (end-to-end) |
| Amazon QuickSight | Hiển thị dashboard và báo cáo | Tạo báo cáo phân tích cho lãnh đạo dựa trên log/metrics từ CloudWatch |
| Amazon CloudFront | CDN phân phối nội dung tĩnh | Tăng tốc độ phản hồi tới người dùng, giảm tải EC2 |



Component interactions và data flow


User gửi request qua CloudFront → truyền đến EC2 instance.


Ứng dụng Spring Boot chạy bằng Docker trên EC2 xử lý request, đồng thời ghi logs và metrics.


CloudWatch Agent trên EC2 thu thập và gửi logs/metrics về CloudWatch.


CloudWatch Alarms được cấu hình để phát hiện ngưỡng bất thường (VD: CPU > 80%, response time > 500ms).


Khi có cảnh báo:


Gửi thông báo qua SNS (Email, SMS).


Kích hoạt AWS Lambda để phản ứng tự động (khởi động lại container, scale EC2, ghi log sự cố...).


DevOps Guru phân tích logs để phát hiện bất thường và đề xuất giải pháp.


X-Ray ghi nhận traces của request để hỗ trợ phân tích sâu khi có sự cố.


QuickSight kết nối CloudWatch để tạo dashboard phân tích lỗi, cảnh áo và hiệu suất hệ thống.


Security architecture và compliance




|  |  |
| --- | --- |
| Thành phần | Biện pháp bảo mật |
| IAM Roles | Phân quyền EC2, Lambda, CloudWatch theo nguyên tắc least privilege |
| CloudWatch Logs | Mã hóa dữ liệu logs at-rest |
| EC2 Security Group | Chỉ cho phép truy cập HTTP/HTTPS và port quản trị qua IP cụ thể |
| Access to QuickSight & DevOps Guru | Quản lý bằng IAM Policy và audit qua CloudTrail |
| ECR Image Security (nếu dùng) | Scan image container, tránh lỗ hổng |



Scalability và performance considerations




|  |  |
| --- | --- |
| Thành phần | Tối ưu mở rộng |
| EC2 | Sử dụng Auto Scaling Group (ASG) nếu cần scale nhiều instance |
| CloudWatch | Hỗ trợ scale không giới hạn logs/metrics |
| Lambda | Tự động scale theo số lượng cảnh báo |
| CloudFront | Caching nội dung giúp giảm tải EC2 |
| Alert Tuning | Phân tích lịch sử metric để thiết lập ngưỡng hợp lý, tránh false alarm |



Integration points với existing systems




|  |  |
| --- | --- |
| Hệ thống hiện tại | Tích hợp |
| Spring Boot App | Đã có log & metrics → dễ tích hợp với CloudWatch |
| MySQL Container | Được monitor qua CloudWatch custom metrics (hoặc Prometheus nếu muốn mở rộng) |
| Docker Compose | Đóng gói và triển khai ứng dụng + DB trên EC2 dễ dàng |
| CI/CD Pipeline (nếu có) | Có thể mở rộng để deploy image mới lên EC2 và update monitoring config qua CDK |


 Technical Implementation


Implementation phases với deliverables




|  |  |  |
| --- | --- | --- |
| Giai đoạn | Nội dung chính | Deliverables |
| P1. Chuẩn bị môi trường | - Cài Docker, CloudWatch Agent trên EC2- Cấu hình IAM, CDK | EC2 instance hoạt động, agent gửi metrics |
| P2. Tích hợp CloudWatch | - Cài và cấu hình agent (CPU, RAM, logs)- Tạo Custom Alarms | Alarms hoạt động và gửi về SNS |
| P3. Anomaly Detection & Automation | - Kích hoạt DevOps Guru- Viết Lambda auto-scale / cảnh báo | Lambda function + DevOps Guru integration |
| P4. Dashboard & Visualisation | - Thiết lập dashboard trên CloudWatch / QuickSight | Dashboard cho metrics & traces |
| P5. Testing & Go-live | - Thực hiện unit test, integration test- Kịch bản mô phỏng lỗi | Test report, ready for production |



Technical requirements (compute, storage, network)






|  |  |
| --- | --- |
| Hạng mục | Mô tả |
| Compute | 1 EC2 instance (t2.medium trở lên), có Docker & Java 21 |
| Storage | 30–50 GB EBS volume, CloudWatch log storage |
| Network | VPC riêng, mở port 8080 (Spring Boot), 3306 (MySQL nội bộ), HTTPS (443) |
| IAM | EC2 instance cần quyền CloudWatchAgentServerPolicy, Lambda cần quyền ECS/EC2 scaling |
| CloudWatch Logs | 7–14 ngày lưu trữ (logGroup: WebEnglishLogs) |




Development approach và methodologies


Chúng tôi áp dụng các phương pháp phát triển hiện đại và thực tiễn tốt nhất của AWS để đảm bảo chất lượng và hiệu quả:


Infrastructure as Code (IaC): Toàn bộ cơ sở hạ tầng AWS (EC2, IAM, CloudWatch Log Groups, Alarms) sẽ được định nghĩa và quản lý bằng AWS CDK (Cloud Development Kit). Điều này giúp tự động hóa việc triển khai, đảm bảo tính nhất quán và dễ dàng quản lý phiên bản.


DevOps: Hệ thống sẽ được tích hợp vào quy trình CI/CD hiện có (nếu áp dụng), cho phép triển khai tự động và liên tục.


Agile Methodology: Dự án sẽ được triển khai theo các sprint ngắn (3–5 ngày), với các buổi review định kỳ sau mỗi giai đoạn để đánh giá tiến độ và điều chỉnh khi cần.


AWS Well-Architected Framework: Chúng tôi tập trung vào các trụ cột chính:


Reliability: Đảm bảo hệ thống có khả năng phục hồi sau lỗi và hoạt động ổn định.


Performance Efficiency: Tối ưu hóa hiệu suất ứng dụng và cơ sở hạ tầng.


Operational Excellence: Tập trung vào tự động hóa, giám sát và khả năng phản ứng.


Testing strategy (unit, integration, performance)




|  |  |  |
| --- | --- | --- |
| Kiểu kiểm thử | Mục tiêu | Công cụ |
| Unit Test | Kiểm tra module log collector, metric parser | JUnit (backend) |
| Integration Test | Test EC2 gửi log lên CloudWatch & SNS hoạt động | Manual / Script |
| Anomaly Simulation | Tạo CPU spike, database lỗi, check alert | stress-ng, X-Ray |
| Performance Test | Load test ứng dụng trên EC2 | Apache JMeter |
| Alert Verification | Kiểm tra Lambda + SNS hoạt động đúng ngưỡng | Test case thủ công |



Deployment plan và rollback procedures


 Deployment Plan:


Triển khai EC2 qua CDK.


Cài đặt Docker, ứng dụng Spring Boot và CloudWatch Agent.


Push Docker image lên ECR (nếu cần).


Kết nối QuickSight, CloudWatch Dashboards.


Kích hoạt DevOps Guru và Lambda phản hồi.


🔁Rollback:


Sử dụng AMI snapshot EC2 để khôi phục cấu hình cũ.


Xoá log group / alarms nếu gặp lỗi cảnh báo sai.


Vô hiệu hóa Lambda tạm thời nếu phản hồi sai ngữ cảnh.


CloudFormation rollback được kích hoạt nếu deploy bằng CDK thất bại.



Configuration management




|  |  |
| --- | --- |
| Hệ thống | Cách quản lý |
| EC2 Instance | Được quản lý bằng AWS CDK (IaC) |
| Docker Containers | Cấu hình môi trường bằng .env & docker-compose |
| CloudWatch Agent | File cấu hình JSON đẩy metrics theo định kỳ |
| Alarms & Metrics | Được version hóa bằng CDK hoặc lưu YAML (Terraform optional) |
| Lambda function | Quản lý version và cập nhật bằng CLI hoặc CDK |



Timeline & Milestones


Project phases breakdown





|  |  |  |  |
| --- | --- | --- | --- |
| Tuần |  | Công việc chính | Milestone & Success Criteria |
| Tuần 1 | P1: Chuẩn bị & Thiết lập hạ tầng | - Cài đặt Docker, CloudWatch Agent trên EC2- Khởi tạo CDK, tạo VPC, EC2 instance- Tạo IAM Roles, cấu hình log group |  EC2 instance hoạt động, agent gửi logs và metrics về CloudWatch |
|  | P2: Monitoring + Logging | - Tạo CloudWatch Alarms- Kiểm thử gửi logs, metrics- Cấu hình Log retention, Streams |  Cảnh báo hoạt động đúng, log xuất hiện trên console |
| Tuần 2 | P3: Tự động hóa & Anomaly Detection | - Tích hợp DevOps Guru- Viết và test Lambda (auto scale, cảnh báo)- Thiết lập SNS, Escalation |  Lambda phản ứng đúng, DevOps Guru phát hiện anomaly test |
|  | P4: Dashboard & Tracing | - Tích hợp X-Ray- Tạo CloudWatch Dashboard, biểu đồ- Kết nối QuickSight |  Dashboard hiển thị realtime, X-Ray có trace, QuickSight nhận dữ liệu |
| Tuần 3 | P5: Testing & Go-live | - Mô phỏng lỗi & phân tích phản hồi- Viết runbook + SOP cho team- Kiểm thử rollback EC2, Lambda |  Pass test cases, runbook đầy đủ, rollback hoạt động |



Key milestones với success criteria




|  |  |
| --- | --- |
| Tuần 1 | P1: Chuẩn bị & Thiết lập hạ tầng
P2: Monitoring + Logging
 |
| Tuần 2 | P3: Tự động hóa & Anomaly Detection
P4: Dashboard & Tracing
 |
| Tuần 3 | P5: Testing & Go-live |



Dependencies identification




|  |  |
| --- | --- |
| Phụ thuộc | Mô tả |
| EC2/CDK setup → Monitoring | Cần EC2 hoạt động trước khi cài agent và log |
| Monitoring → Alarm → Lambda | Alarms hoạt động mới test Lambda phản ứng được |
| Logs → Dashboard / QuickSight | Phải có dữ liệu thì mới tạo dashboard được |
| DevOps Guru → Anomaly Detection | Cần log ổn định mới học được hành vi bất thường |



Critical path analysis


Tạo EC2 & setup → Cấu hình CloudWatch → Tạo alarm → Kết nối Lambda & SNS → Mô phỏng sự cố → DevOps Guru học hành vi → Phân tích kết quả → Rollout.


Resource allocation plan




|  |  |
| --- | --- |
| Nhân lực | Nhiệm vụ |
| DevOps Engineer | CDK, EC2, Lambda, Logs |
| Backend Developer | Spring Boot log config, Dockerfile |
| Data Analyst | QuickSight dashboard, trace review |



Buffer time cho risks


· Buffer: 2 ngày cuối Tuần 3 để xử lý:


AWS service issues (quota, region delay)


IAM policy thiếu / không đủ quyền


Lambda phản ứng sai ngữ cảnh


· Giảm rủi ro bằng:


AMI snapshot EC2 định kỳ


Rollback CDK stack


Tách riêng môi trường staging/test


Budget Estimation


AWS infrastructure costs (monthly/annual)




|  |  |
| --- | --- |
| Dịch vụ | Chi phí hàng tháng (ước tính) |
| Amazon EC2 | ~$28 (t2.medium, on-demand) |
| Amazon EBS (30GB) | ~$3 |
| CloudWatch Logs & Metrics | ~$10 |
| AWS Lambda | ~$1–2 |
| Amazon SNS | ~$1 |
| AWS DevOps Guru | ~$15–20 |
| Amazon QuickSight (Standard) | ~$9 |
| Amazon CloudFront (optional) | ~$5 |
| Tổng cộng (hàng tháng) | ~$70–80 |
| Tổng cộng (hàng năm) | ~$960 |



Development costs (one-time)






|  |  |  |
| --- | --- | --- |
| Hạng mục | Ước tính chi phí | Ghi chú |
| DevOps Engineer (15 ngày) | ~$1,500 | $100/ngày |
| Backend Developer (4 ngày) | ~$400 | Tích hợp logs, metrics |
| Data Analyst (3 ngày) | ~$300 | Dashboard, QuickSight |



Third-party services và licenses




|  |  |  |
| --- | --- | --- |
| Dịch vụ | Chi phí | Ghi chú |
| PagerDuty (Standard) | ~$21/người/tháng | Dự kiến dùng 1 user (chỉ nếu mở rộng) |
| Tổng cộng (nếu áp dụng) | ~$250/năm | Không bắt buộc trong giai đoạn đầu |



Operational costs (ongoing)




|  |  |  |
| --- | --- | --- |
| Hạng mục | Ước tính hàng tháng | Ghi chú |
| Monitoring review & tuning | $100 | 4h/tháng DevOps kiểm tra logs, dashboard |
| Alert audit & DevOps training | $50 | Cập nhật playbook, runbook định kỳ |
| Tổng cộng | ~$150/tháng | ~$1,800/năm |



ROI calculation và break-even analysis


ROI Scenario:


Trước triển khai: downtime ~6 sự cố/năm × $500/sự cố = $3,000 tổn thất/năm


Sau triển khai: giảm 60–80% downtime → tiết kiệm ~$2,000–2,400/năm


Break-even:


Chi phí đầu tư ban đầu: ~$2,500 (dev) + ~$960 (infra) = ~$3,460


Thời gian hoàn vốn (Break-even): ~18–20 tháng


Cost optimization strategies




|  |  |
| --- | --- |
| Giải pháp | Mô tả |
| Sử dụng EC2 Spot Instances | Giảm chi phí compute 40–60% nếu ứng dụng cho phép gián đoạn |
| Log retention policy | Tự động xóa logs sau 7 ngày để giảm chi phí CloudWatch |
| Tối ưu Lambda function | Chỉ dùng khi cần, tránh trigger không cần thiết |
| Chỉ kích hoạt DevOps Guru theo giờ làm việc | Tránh tính phí liên tục nếu traffic thấp |



Risk Assessment


Risk identification (technical, business, operational)





|  |  |
| --- | --- |
| Loại rủi ro | Mô tả |
| Technical | CloudWatch agent không hoạt động đúng, Lambda không phản hồi cảnh báo, sai cấu hình IAM |
| Business | Dự án triển khai trễ → ảnh hưởng tiến độ mở rộng WebEnglish |
| Operational | Nhân lực thiếu kinh nghiệm AWS/CDK, cảnh báo bị bỏ sót hoặc spam |
| Cost-related | DevOps Guru hoặc logs phát sinh chi phí vượt dự kiến |
| Security | Lỗi IAM cho phép truy cập trái phép vào logs hoặc SNS |



Impact assessment và probability analysis




|  |  |  |  |
| --- | --- | --- | --- |
| Rủi ro | Mức ảnh hưởng | Xác suất | Mức độ nghiêm trọng |
| IAM policy sai gây lỗi Lambda | Cao | Trung bình | Cao |
| DevOps Guru vượt quota chi phí | Trung bình | Trung bình | Trung bình |
| Log không được gửi lên CloudWatch | Cao | Cao | Rất cao |
| Cảnh báo giả gây "alert fatigue" | Trung bình | Cao | Cao |



Risk matrix với prioritization




|  |  |  |  |
| --- | --- | --- | --- |
|  | Xác suất thấp | Xác suất trung bình | Xác suất cao |
| Ảnh hưởng cao | 🔒 IAM Role sai dẫn đến ECS/Lambda lỗi quyền |  Lambda timeout do payload lớn / retry liên tục | 📉 Mất log CloudWatch vì giới hạn lưu trữ |
| Ảnh hưởng trung bình | — | 💰 DevOps Guru vượt ngân sách do theo dõi quá rộng | 🔔 Alert fatigue – cảnh báo ồ ạt, khó xử lý |
| Ảnh hưởng thấp | — | 👨‍💻 Thiếu nhân lực xử lý escalation ngoài giờ | — |



Mitigation strategies cho each risk




|  |  |
| --- | --- |
| Rủi ro | Chiến lược giảm thiểu |
| IAM policy sai | Kiểm tra kỹ role qua IAM Policy Simulator, dùng CDK cho versioning IAM |
| Log không gửi được | Test agent trước production, giám sát bằng chính CloudWatch |
| Lambda timeout | Tối ưu logic Lambda, tăng thời gian timeout nếu cần |
| Alert spam | Thiết lập ngưỡng cảnh báo hợp lý, dùng anomaly detection thay vì cảnh báo cố định |
| Thiếu nhân sự | Dự phòng tài nguyên hỗ trợ nội bộ, document SOP rõ ràng |



Contingency plans




|  |  |
| --- | --- |
| Tình huống xấu | Phương án dự phòng |
| CloudWatch agent lỗi | Dùng script log thủ công / chuyển sang Prometheus tạm thời |
| Lambda không phản hồi | Chuyển sang xử lý tay tạm thời qua SNS + Runbook |
| DevOps Guru bị disable/quota | Chuyển sang phân tích metric thủ công (Logs Insights) |
| Cảnh báo sai ngưỡng | Rollback alarm config qua CDK version hoặc YAML |



Monitoring và escalation procedures




|  |  |
| --- | --- |
| Mục tiêu | Kế hoạch giám sát |
| Giám sát hoạt động cảnh báo | Dashboard CloudWatch theo dõi số lượng alert |
| Log agent | Metric LogDeliveryErrors được giám sát mỗi giờ |
| Lambda fail | Gửi error lên SNS topic riêng, theo dõi trong X-Ray |
| Escalation | Cấp 1 (DevOps), cấp 2 (PM), cấp 3 (CTO) qua email/PagerDuty nếu alert nghiêm trọng trong > 15 phút |



 Expected Outcomes


Success metrics (technical và business)




|  |  |  |
| --- | --- | --- |
| Loại chỉ số | Chỉ số cụ thể | Mục tiêu |
| Technical | Uptime hệ thống | > 99.9% |
|  | MTTR (Mean Time to Resolution) | < 15 phút/sự cố |
|  | Alert accuracy (precision) | > 90% (giảm false alarm) |
|  | Lambda response success rate | > 95% |
| Business | Giảm downtime hàng quý | ≥ 60% |
|  | Sự hài lòng người dùng sau sự cố | > 90% (CSAT survey) |



Short-term benefits (0-6 months)




|  |  |
| --- | --- |
| Lợi ích | Tác động |
| Giảm đáng kể thời gian xử lý sự cố | Từ hàng giờ → còn dưới 15 phút |
| Phát hiện sớm bất thường | Nhờ CloudWatch + DevOps Guru |
| Có hệ thống cảnh báo đa cấp | Đảm bảo sự cố không bị bỏ sót |
| Tăng độ tin cậy nội bộ | DevOps team bớt phụ thuộc xử lý tay |



Medium-term benefits (6-18 months)


 




|  |  |
| --- | --- |
| Lợi ích | Tác động |
| Tối ưu hóa vận hành liên tục | Giảm alert spam, chi phí log |
| Hiểu rõ hành vi hệ thống | Thông qua Dashboard & X-Ray |
| Cải thiện SLA cho khách hàng | Tăng uy tín với người dùng doanh nghiệp |
| Giảm thiểu chi phí downtime | ROI dự kiến > 60% đầu tư ban đầu |



Long-term value (18+ months)




|  |  |
| --- | --- |
| Lợi ích chiến lược | Tác động |
| Sẵn sàng scale hệ thống lớn hơn | Có nền tảng auto-monitoring ổn định |
| Nền tảng tích hợp AI/ML monitoring | Có thể tích hợp thêm SageMaker anomaly |
| Định hình quy trình DevSecOps hoàn chỉnh | Đưa security và automation vào chuẩn vận hành |
| Khả năng mở rộng sang nhiều dịch vụ khác | Áp dụng mô hình giám sát này cho các microservices khác của WebEnglish |



User experience improvements


Giảm thời gian lỗi ứng dụng xuất hiện trên giao diện người dùng (dưới 1 phút).


Tránh được sự gián đoạn đột ngột nhờ cảnh báo trước.


Người dùng không cần phản hồi để phát hiện lỗi – hệ thống tự động nhận diện.


Nâng cao độ tin cậy và hài lòng người học, đặc biệt trong giờ cao điểm.


Strategic capabilities gained


Giao diện hiện đại, dễ dùng


Xác thực bảo mật nhưng không gây khó chịu


Phản hồi nhanh, mượt


Hỗ trợ đa nền tảng (web, mobile)


Cập nhật tính năng dựa trên góp ý người dùng







