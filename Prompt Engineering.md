Prompt Engineering – Từ Mơ hồ thành Pro

Tài liệu hướng dẫn này cung cấp lộ trình cơ bản về Generative AI và kỹ thuật Prompt Engineering. Cho dù bạn mới bắt đầu hay đã có kinh nghiệm, nội dung dưới đây sẽ giúp bạn nắm vững khái niệm nền tảng và các kỹ thuật nâng cao để chuyển từ những prompt mơ hồ sang prompt “pro”. Chúng ta sẽ lần lượt tìm hiểu về Generative AI, cách viết prompt hiệu quả, cấu trúc của một prompt, và các kỹ thuật prompting quan trọng như Instruction Prompting, Role Prompting và Prompting dựa trên ví dụ (Zero-shot, One-shot, Few-shot), kèm ví dụ minh họa cụ thể cho từng phần.

Giới thiệu: AI và Generative AI

Trí tuệ nhân tạo (AI) là lĩnh vực công nghệ phát triển các hệ thống máy móc có thể thực hiện những nhiệm vụ đòi hỏi trí thông minh như con người. Ví dụ, AI có thể nhận diện giọng nói và hình ảnh, tạo văn bản hoặc âm thanh, ra quyết định, thậm chí chơi cờ ở cấp độ cao. Trong đời sống hàng ngày, AI hiện diện khắp nơi:

Trợ lý ảo (Siri, Alexa, Google Assistant) hiểu lệnh thoại và phản hồi yêu cầu của bạn.

Hệ thống gợi ý trên Netflix, YouTube, Spotify đề xuất nội dung dựa trên thói quen của bạn.

Mạng xã hội dùng AI để lọc và hiển thị những nội dung phù hợp với sở thích người dùng.

Machine Learning (ML) là phương pháp phổ biến để hiện thực hóa AI. ML giúp máy tính học từ dữ liệu. Quá trình học gồm: thu thập dữ liệu lớn, huấn luyện mô hình (thường là mạng nơ-ron), đánh giá – tinh chỉnh mô hình, và cuối cùng là suy luận (dự đoán trên dữ liệu mới). Mô hình sẽ tự điều chỉnh các tham số bên trong dựa trên dữ liệu huấn luyện để ngày càng cải thiện hiệu suất. Generative AI (AI tạo sinh) là một nhánh đặc biệt của AI. Đây là những mô hình học máy có khả năng tạo ra nội dung mới dựa trên kiến thức đã học từ dữ liệu khổng lồ. Thay vì chỉ phân loại hay dự đoán, Generative AI có thể sinh ra văn bản, hình ảnh, âm thanh hoặc video chưa từng có trước đây. Một số đặc trưng và ứng dụng nổi bật của Generative AI gồm:

Tạo văn bản: Mô hình ngôn ngữ lớn (Large Language Model – LLM) như ChatGPT có thể viết đoạn văn, trả lời câu hỏi, sáng tác truyện, soạn email… dựa trên prompt của người dùng.

Tạo hình ảnh: Mô hình như DALL-E biến mô tả bằng chữ thành hình ảnh độc đáo, chi tiết.

Tạo âm thanh/nhạc: AI có thể sáng tác nhạc hoặc giả lập giọng nói theo yêu cầu.

Tạo video: Các hệ thống có thể tạo đoạn video ngắn hoặc chỉnh sửa video dựa trên mô tả.

Sinh dữ liệu tổng hợp: Tạo ra dữ liệu (ví dụ như hình ảnh, văn bản giả lập) để phục vụ huấn luyện mô hình khác hoặc kiểm thử phần mềm.

Mô hình đa phương thức: Kết hợp nhiều loại dữ liệu (văn bản + hình ảnh + âm thanh) để tạo ra nội dung phong phú.

Generative AI đang tạo ra những thay đổi lớn trong nhiều lĩnh vực nhờ khả năng độc đáo này. Tuy nhiên, để khai thác tốt sức mạnh của Generative AI, chúng ta cần học cách “giao tiếp” hiệu quả với các mô hình – đó chính là Prompt Engineering.

Bắt đầu với ChatGPT – Công cụ GenAI phổ biến

Trong hướng dẫn này, chúng ta sẽ chủ yếu sử dụng ChatGPT (một chatbot AI mạnh mẽ do OpenAI phát triển) để thực hành. ChatGPT là ví dụ tiêu biểu của một mô hình Generative AI về văn bản, rất phổ biến và dễ sử dụng. Giao diện của ChatGPT giống một hộp chat: bạn nhập prompt (lời nhắc/hướng dẫn) và AI sẽ trả lời ngay. Thiết lập ChatGPT rất đơn giản: truy cập trang chat.openai.com, tạo tài khoản (nếu chưa có), rồi đăng nhập. Ngoài ra, bạn có thể dùng ứng dụng di động ChatGPT (iOS/Android) với giao diện tương tự. Sau khi thiết lập, hãy thử một vài prompt cơ bản đến phức tạp để thấy khả năng của AI:

Truy vấn đơn giản: Ví dụ, hỏi “Cỏ có màu gì?” – AI sẽ đáp: “Cỏ thường có màu xanh lá cây.”

Nhiệm vụ phức tạp hơn: Yêu cầu “Tóm tắt bài viết này” (kèm nội dung bài viết) – AI có thể đưa ra bản tóm tắt chính xác vài câu.

Giải toán: Nhập “Giải phương trình 2x + 5 = 11” – AI sẽ giải và trả lời: “x = 3.”

Qua những thử nghiệm này, bạn sẽ thấy rằng chất lượng câu trả lời của AI phụ thuộc trực tiếp vào cách bạn đặt prompt: prompt càng rõ ràng, cụ thể, có định hướng, thì kết quả càng sát mong đợi. Đó là lý do Prompt Engineering ra đời như một kỹ năng quan trọng.

Prompt và Prompt Engineering là gì?

Prompt hiểu đơn giản là đầu vào hoặc hướng dẫn mà bạn đưa cho mô hình AI để nhận lại phản hồi. Một prompt có thể chỉ là một câu hỏi ngắn, hoặc cũng có thể là một đoạn hướng dẫn chi tiết kèm ngữ cảnh, vai trò, phong cách viết, định dạng yêu cầu,… Mục tiêu của prompt là mô tả đúng nhiệm vụ bạn muốn AI thực hiện và cách thức bạn muốn nhận câu trả lời. Prompt Engineering là nghệ thuật và kỹ thuật viết prompt sao cho hiệu quả nhất, nhằm “điều khiển” AI tạo ra kết quả bạn mong muốn. Nói cách khác, thay vì lập trình bằng mã lệnh, chúng ta “lập trình” cho AI thông qua ngôn ngữ tự nhiên. Prompt Engineering bao gồm: hiểu rõ cách AI xử lý ngôn ngữ, nắm được các thành phần của một prompt tốt, và áp dụng các chiến lược đặc biệt (như gán vai trò cho AI, cho ví dụ minh họa, v.v.) để hướng dẫn mô hình. Tại sao Prompt Engineering quan trọng? Vì các mô hình Generative AI tuy rất thông minh, nhưng không tự đọc suy nghĩ của chúng ta – chúng chỉ phản hồi dựa trên prompt được cung cấp. Một prompt thiếu rõ ràng hoặc mơ hồ có thể dẫn đến câu trả lời sai hoặc không liên quan. Ngược lại, một prompt được “engineer” tốt sẽ giúp AI hiểu đúng yêu cầu và bối cảnh, từ đó phản hồi chính xác, đúng trọng tâm hơn. Thực tế cho thấy, cải thiện prompt có thể cải thiện đáng kể chất lượng đầu ra của AI.

Ví dụ: Cải thiện prompt để có kết quả tốt hơn

Giả sử bạn muốn AI viết một đoạn giới thiệu marketing về một sản phẩm AI mới.

Prompt ban đầu (mơ hồ): “Hãy soạn một bản tóm tắt tiếp thị cho một công cụ AI mới hỗ trợ các công ty tự động hóa nhiệm vụ.”

Kết quả: AI có thể tạo ra một đoạn giới thiệu rất chung chung vì prompt chưa nêu rõ chi tiết quan trọng nào.

Prompt đã tinh chỉnh (cụ thể hơn): “Soạn một bản tóm tắt tiếp thị dài ~100 từ cho công cụ AI mới tên là TaskBot. Công cụ này giúp tự động hóa các nhiệm vụ lặp lại cho các doanh nghiệp nhỏ trong lĩnh vực bán lẻ và y tế, nhấn mạnh hiệu quả và tiết kiệm chi phí.”

Kết quả: AI sẽ tạo một đoạn giới thiệu cụ thể, nêu bật tên sản phẩm (TaskBot), đối tượng khách hàng (doanh nghiệp nhỏ ngành bán lẻ, y tế), và ưu thế chính (hiệu quả, tiết kiệm chi phí). Nội dung đáp ứng đúng mong đợi hơn nhiều so với prompt ban đầu.

Như vậy, bằng cách thêm thông tin bối cảnh, độ dài mong muốn, tên riêng và các điểm nhấn, prompt thứ hai đã “dẫn dắt” AI cho câu trả lời sát nhu cầu. Đây chính là sức mạnh của prompt engineering: từ một ý tưởng mơ hồ, chúng ta tinh chỉnh thành hướng dẫn rõ ràng để AI hiểu và thực hiện.

Cách viết Prompt hiệu quả (Best Practices)

Viết prompt là một quá trình sáng tạo kết hợp tư duy logic. Dưới đây là một số mẹo và kỹ thuật thực tế giúp prompt của bạn hiệu quả hơn, cho dù bạn đang yêu cầu AI viết văn, tạo mã hay vẽ tranh: 1. Cụ thể và Rõ ràng: Hãy diễn đạt yêu cầu một cách chi tiết, tránh chung chung. Sử dụng động từ hành động mạnh và từ ngữ rõ nghĩa.

Ví dụ: Thay vì prompt mơ hồ “Cho tôi biết về loài cỏ”, hãy thử cụ thể hơn:

markdown

Sao chép

Chỉnh sửa

\*\*Prompt\*\*: Phân tích \*\*đặc điểm của cỏ ở vùng ôn đới\*\*, tập trung vào:

1. Sự \*\*thay đổi màu sắc theo mùa\*\*
1. \*\*Chiều cao trung bình\*\* của cỏ
1. \*\*Các loài cỏ phổ biến\*\*

Định dạng câu trả lời dưới dạng các gạch đầu dòng.

Prompt trên xác định rõ chủ đề (cỏ ôn đới), các ý cần đề cập (3 ý), và định dạng mong muốn (gạch đầu dòng). AI vì thế dễ hiểu và trả lời đầy đủ hơn. Khi viết prompt, hãy luôn nghĩ: Mình có thể bổ sung chi tiết nào để AI hiểu đúng và đủ? 2. Tổ chức cấu trúc prompt hợp lý: Nếu yêu cầu phức tạp, đừng ngại chia nhỏ và trình bày có thứ tự. Bạn có thể dán nhãn các phần của prompt để tăng tính rõ ràng, chẳng hạn như Ngữ cảnh, Nhiệm vụ, Ràng buộc, Định dạng… Việc này giống như cung cấp “dàn ý” cho AI.

Ví dụ:

markdown

Sao chép

Chỉnh sửa

\*\*Prompt\*\*:

\*\*Ngữ cảnh:\*\* Bạn đang phân tích một bài báo nghiên cứu khoa học.

\*\*Nhiệm vụ:\*\* Hãy tạo một \*\*bản tóm tắt\*\* của bài báo.

\*\*Ràng buộc:\*\* Bản tóm tắt tối đa \*\*100 từ\*\*.

\*\*Định dạng:\*\* Sử dụng cấu trúc:

- \*\*Phát hiện chính\*\*
- \*\*Phương pháp chính\*\*
- \*\*Ý nghĩa\*\* của nghiên cứu.

Ở đây, prompt đã được cấu trúc rõ ràng theo các nhãn (Ngữ cảnh, Nhiệm vụ, v.v.). Điều này giúp AI biết chính xác vai trò của từng đoạn: đâu là bối cảnh, đâu là yêu cầu chính, giới hạn độ dài bao nhiêu, và cần định dạng kết quả ra sao.

Mẹo: Luôn đặt nhiệm vụ chính (điều bạn muốn AI thực hiện) một cách dễ nhận thấy, thường là sau phần ngữ cảnh và các hướng dẫn phụ. Trình tự hợp lý sẽ đảm bảo AI không bị rối và tập trung vào đúng việc cần làm. (Ví dụ, nếu đặt nhiệm vụ cuối cùng, AI sẽ xử lý hết ngữ cảnh và hướng dẫn trước khi đưa ra kết quả, tránh lan man). 3. Cung cấp ngữ cảnh cần thiết: AI hoạt động hiệu quả hơn khi hiểu bối cảnh của yêu cầu. Vì vậy, hãy cho mô hình biết những thông tin nền quan trọng hoặc giả định vai trò của người dùng. Ngữ cảnh có thể là đối tượng khán giả, mục tiêu của nhiệm vụ, hoặc tình huống cụ thể.

Ví dụ: Bạn muốn giải thích về quá trình quang hợp:

markdown

Sao chép

Chỉnh sửa

\*\*Prompt\*\*:

\*\*Ngữ cảnh:\*\* Tôi là \*\*giáo viên Sinh học lớp 10\*\* đang chuẩn bị bài giảng về quá trình \*\*quang hợp\*\*.

\*\*Đối tượng học sinh:\*\* Các em học sinh lớp 10 (15-16 tuổi).

\*\*Yêu cầu:\*\* Giải thích quá trình \*\*quang hợp\*\* sao cho:

- Sử dụng \*\*phép so sánh đơn giản, gần gũi\*\*.
- Bao gồm \*\*3 ý chính\*\* của quá trình.
- \*\*Tránh dùng thuật ngữ\*\* chuyên môn phức tạp.

\*\*Độ dài:\*\* 2-3 đoạn văn ngắn.

Với prompt trên, AI hiểu rõ vai trò (giáo viên), người đọc mục tiêu (học sinh 15-16 tuổi), chủ đề (quang hợp) và các yêu cầu cụ thể về cách giải thích. Nhờ vậy, câu trả lời sẽ phù hợp với đối tượng học sinh, dễ hiểu và đủ ý. 4. Sử dụng ví dụ (few-shot) khi cần: Đôi khi chỉ mô tả nhiệm vụ bằng lời là chưa đủ, đặc biệt nếu bạn muốn kết quả theo một định dạng hay phong cách nhất định. Trong trường hợp này, hãy đưa ra ví dụ minh họa ngay trong prompt. Cho AI thấy mẫu đầu vào – đầu ra mong đợi, mô hình sẽ học theo mẫu đó (kỹ thuật này gọi là In-Context Learning). Bạn có thể cung cấp một ví dụ (one-shot) hoặc nhiều ví dụ (few-shot) tùy nhu cầu.

Ví dụ (few-shot): Yêu cầu AI chuyển đổi ngày tháng sang định dạng chuẩn ISO:

markdown

Sao chép

Chỉnh sửa

\*\*Prompt\*\*: Chuyển các ngày sau sang định dạng \*\*YYYY-MM-DD\*\*. Hãy làm theo mẫu ví dụ:

\*\*Ví dụ:\*\*

Đầu vào: March 15, 2024

Đầu ra: 2024-03-15

Đầu vào: December 31, 2023

Đầu ra: 2023-12-31

\*\*Bây giờ chuyển đổi:\*\* January 1, 2025

Đầu ra:

Trong prompt này, hai ví dụ cụ thể đã được cung cấp. AI sẽ hiểu rằng cần lấy phần “Đầu vào” và biến đổi thành “Đầu ra” theo đúng mẫu (tháng chữ sang tháng số, v.v.). Nhờ vậy, khi gặp “January 1, 2025”, mô hình sẽ áp dụng quy tắc từ ví dụ và trả lời: 2025-01-01. Việc cung cấp ví dụ đặc biệt hữu ích khi nhiệm vụ phức tạp hoặc đòi hỏi định dạng kết quả nghiêm ngặt. 5. Lặp lại và tinh chỉnh: Viết prompt hiệu quả thường không hoàn hảo ngay lần đầu. Hãy áp dụng phương pháp thử – sai – sửa: nếu phản hồi AI chưa như ý, đừng ngần ngại chỉnh sửa prompt rồi chạy lại. Mỗi lần lặp, bạn có thể bổ sung thêm chi tiết, làm rõ yêu cầu hoặc loại bỏ phần gây hiểu lầm.

Ví dụ:

Lần đầu bạn prompt: “Tóm tắt bài viết này.” – AI tóm tắt quá sơ sài.

Bạn tinh chỉnh: “Tóm tắt bài viết này trong 3 câu, tập trung vào những thách thức chính được thảo luận.” – Kết quả chi tiết và đúng trọng tâm hơn hẳn.

Luôn xem xét kỹ phản hồi của AI: nó thiếu thông tin gì? có hiểu sai ý không? Sau đó, cập nhật prompt tương ứng. Quá trình tinh chỉnh liên tục chính là cách một prompt engineer nâng cao chất lượng đầu ra. Nhớ rằng ngay cả chuyên gia cũng phải thử nghiệm nhiều lần – nên bạn cứ yên tâm điều chỉnh cho đến khi đạt kết quả mong muốn. Tóm lại, một prompt hiệu quả thường có đặc điểm: cụ thể, có cấu trúc rõ ràng, cung cấp đủ ngữ cảnh, (nếu cần) có ví dụ minh họa, và sẵn sàng được điều chỉnh qua các lần tương tác. Tiếp theo, chúng ta sẽ đi sâu vào cấu trúc của một prompt và các kỹ thuật prompting nâng cao giúp bạn kiểm soát tốt hơn nữa đầu ra của AI.

Cấu trúc Chính của một Prompt

Mặc dù không có “khuôn mẫu” bắt buộc cho mọi prompt (vì tính sáng tạo linh hoạt của ngôn ngữ tự nhiên), nhưng hầu hết các prompt hiệu quả đều bao gồm một số thành phần chính. Hiểu và sử dụng tốt các thành phần này sẽ giúp bạn xây dựng prompt mạnh mẽ hơn. Dưới đây là 5 thành phần quan trọng và vai trò của chúng:

Task (Nhiệm vụ chính): Đây là yêu cầu cốt lõi bạn muốn AI thực hiện – ví dụ: trả lời câu hỏi, viết đoạn văn, dịch thuật, tính toán, tóm tắt, v.v. Nên diễn đạt nhiệm vụ một cách rõ ràng, tốt nhất là dùng động từ mạnh ở đầu (viết, giải thích, liệt kê, phân tích…). Task chính là trái tim của prompt, nên hãy chắc chắn người (và AI) đọc prompt nhận ra ngay “bạn cần AI làm gì”.

Context (Ngữ cảnh): Cung cấp bối cảnh hoặc thông tin nền sẽ giúp AI hiểu sâu hơn yêu cầu. Ngữ cảnh có thể là: vai trò bạn muốn AI đảm nhận (giáo viên, chuyên gia, v.v.), đối tượng người đọc, tình huống giả định, hoặc dữ liệu nền (ví dụ đưa hẳn một đoạn văn bản để AI dựa vào đó trả lời). Thành phần này không phải lúc nào cũng cần, nhưng với các nhiệm vụ phức tạp hoặc chuyên biệt, context tốt là chìa khóa để AI không bị lạc hướng.

Examples (Ví dụ minh họa): Như đã đề cập ở phần trên, ví dụ trong prompt đóng vai trò “mẫu hướng dẫn”. Bằng cách cho AI thấy một (hoặc vài) ví dụ về đầu vào và đầu ra mong muốn, bạn giúp mô hình học được cách thực hiện nhiệm vụ ngay trong lần tương tác đó (nhờ khả năng In-Context Learning). Examples đặc biệt hữu ích cho các tác vụ như: định dạng output, dịch thuật theo phong cách nhất định, phân loại, hay bất kỳ nhiệm vụ nào có quy tắc. Lưu ý: chỉ cung cấp ví dụ thật cần thiết, vì quá nhiều ví dụ sẽ làm prompt dài và có thể gây quá tải ngữ cảnh.

Role (Vai trò giả định của AI): Đây là kỹ thuật gán vai trò, cho AI “đóng vai” một nhân vật hay chuyên gia cụ thể. Bản chất Role là một dạng ngữ cảnh đặc biệt, nhưng đáng tách riêng vì hiệu quả nổi bật: Khi AI nhập vai, nó sẽ điều chỉnh phong cách, giọng điệu và thậm chí ưu tiên thông tin phù hợp với vai đó. Ví dụ, bắt đầu prompt bằng “Bạn là một nhà phê bình ẩm thực khó tính... ” sẽ khiến văn phong trả lời khác hẳn so với “Bạn là một chuyên gia dinh dưỡng...” dù cùng nói về món ăn. Phần Role nên đặt ở đầu prompt (nếu sử dụng), để thiết lập “nhân vật” cho AI trước khi nó thực hiện nhiệm vụ.

Format (Định dạng đầu ra mong muốn): Nếu bạn cần câu trả lời theo định dạng cụ thể, hãy nói rõ điều đó trong prompt. Định dạng có thể bao gồm: độ dài (số từ, số câu, số đoạn), kiểu văn bản (dạng bảng, danh sách gạch đầu dòng, đoạn văn, mã code, JSON, v.v.), hoặc bố cục (ví dụ: “Trả lời theo cấu trúc: Ưu điểm – Nhược điểm – Kết luận”). Xác định format ngay trong prompt sẽ giúp AI xuất kết quả đúng kiểu bạn muốn, tránh việc bạn phải chỉnh sửa thủ công sau.

Khi kết hợp các thành phần trên, hãy lưu ý thứ tự logic: Thông thường, ta cung cấp Context và/hoặc Role trước (thiết lập bối cảnh), sau đó nêu Task, và cuối cùng là các yêu cầu về Format hoặc đưa Examples minh họa. Tuy nhiên, tùy trường hợp cụ thể mà bạn có thể linh hoạt. Quan trọng là đảm bảo mỗi thành phần đều phục vụ mục đích làm cho yêu cầu rõ ràng hơn chứ không gây rối. Ví dụ tổng hợp: Dưới đây là một prompt mẫu kết hợp nhiều thành phần, minh họa cách chúng hoạt động cùng nhau:

markdown

Sao chép

Chỉnh sửa

\*\*Bạn là một nhà phân tích dữ liệu\*\* dày dạn kinh nghiệm (Role).

Tôi sẽ cung cấp cho bạn dữ liệu thô về doanh số bán hàng quý vừa rồi. \*\*Nhiệm vụ của bạn là\*\* viết một \*\*báo cáo tóm tắt\*\* (Task) nêu rõ:

- Xu hướng doanh số theo tháng (tăng/giảm thế nào)
- Sản phẩm bán chạy nhất và kém nhất
- Đề xuất cải thiện cho quý tới

\*\*Dữ liệu:\*\* (Context) Tháng 1: 1200 đơn, Tháng 2: 1100 đơn, Tháng 3: 1350 đơn, ... (tiếp tục liệt kê dữ liệu).

\*\*Yêu cầu định dạng\*\*: Viết báo cáo dưới dạng văn bản học thuật, gồm \*\*3 đoạn\*\* tương ứng với 3 gạch đầu dòng trên, có thể dùng số liệu minh họa. (Format)

Trong prompt này:

Mở đầu gán Role “nhà phân tích dữ liệu” để câu trả lời có giọng điệu chuyên nghiệp, sâu sắc.

Phần Task nhấn mạnh “viết báo cáo tóm tắt” và liệt kê cụ thể 3 yêu cầu nội dung (giống dàn ý cần có trong báo cáo).

Context cung cấp dữ liệu thô về doanh số để AI dựa vào đó phân tích (nếu không có dữ liệu, AI sẽ phải tưởng tượng, kém chính xác).

Cuối cùng, yêu cầu Format đảm bảo báo cáo có đúng 3 đoạn, văn phong học thuật, giúp output đúng khuôn mẫu cần thiết.

Với cấu trúc rõ ràng như vậy, khả năng cao AI sẽ tạo ra một báo cáo sát dữ liệu và yêu cầu hơn so với việc bạn chỉ nói “hãy phân tích doanh số quý trước”. Như vậy, nắm vững các thành phần Task – Context – Examples – Role – Format và cách sắp xếp chúng sẽ giúp bạn “lập trình” cho AI một cách tường minh. Tiếp theo, chúng ta chuyển sang các kỹ thuật prompting nâng cao, vốn tận dụng chính các thành phần trên một cách sáng tạo để giải quyết những tình huống cụ thể.

Các Kỹ thuật Prompting Nâng cao

Trong phần này, chúng ta sẽ khám phá ba kỹ thuật quan trọng trong Prompt Engineering giúp giải quyết các loại nhiệm vụ đa dạng: Instruction Prompting, Role Prompting và Prompting dựa trên ví dụ (Zero-shot/Few-shot). Mỗi kỹ thuật sẽ được định nghĩa, phân tích ưu nhược điểm và minh họa bằng ví dụ cụ thể.

1. Instruction Prompting (Prompt theo hướng dẫn chi tiết)

Instruction Prompting là kỹ thuật viết prompt dưới dạng hướng dẫn hoặc mệnh lệnh rõ ràng, chi tiết để mô hình AI thực hiện một nhiệm vụ phức tạp. Thay vì chỉ hỏi một câu đơn giản, ta cung cấp cho AI một “bản hướng dẫn” tuần tự về những gì cần làm. Kỹ thuật này tận dụng khả năng của các mô hình ngôn ngữ lớn trong việc hiểu và làm theo hướng dẫn ngôn ngữ tự nhiên, ngay cả với nhiệm vụ chúng chưa từng được huấn luyện cụ thể. Chìa khóa của instruction prompting là trình bày yêu cầu mạch lạc, súc tích và có cấu trúc, giúp AI dễ “tuân lệnh”. Vì sao instruction prompting hiệu quả? Bởi vì một lời hướng dẫn rõ ràng sẽ định hướng suy nghĩ của AI tốt hơn, giảm thiểu sự mơ hồ. Với những nhiệm vụ đa bước hoặc phức tạp, instruction prompting cho phép ta “dẫn dắt” mô hình qua từng phần công việc. Ví dụ tình huống: Bạn có một văn bản và muốn AI tự động loại bỏ mọi thông tin nhận dạng cá nhân (PII) trong đó (như tên người, số điện thoại, email…), thay thế bằng placeholder thích hợp. Đây là một tác vụ gồm nhiều bước (tìm PII -> loại bỏ -> thay bằng ký hiệu), phù hợp để dùng instruction prompt. Ví dụ: Loại bỏ thông tin cá nhân khỏi email:

markdown

Sao chép

Chỉnh sửa

\*\*Prompt:\*\* Đọc nội dung email dưới đây và \*\*loại bỏ mọi thông tin nhận dạng cá nhân (PII)\*\*. Thay thế chúng bằng placeholder phù hợp trong ngoặc vuông.

Ví dụ: Tên riêng thay bằng [NAME], số điện thoại thay bằng [PHONE], email thay bằng [EMAIL], tên công ty thay bằng [COMPANY].

Nội dung email:

"Xin chào \*\*John Doe\*\*,

Tôi là \*\*Jane Smith\*\*, nhân viên kinh doanh tại \*\*Công ty ABC\*\*. Số điện thoại của tôi là \*\*090-123-4567\*\* và email là \*\*[email protected]\*\*. ..."

\*\*Yêu cầu:\*\* Đưa ra nội dung email đã được ẩn PII, giữ nguyên ngữ nghĩa gốc.

AI Output (kết quả mong đợi):

"Xin chào [NAME], Tôi là [NAME], nhân viên kinh doanh tại [COMPANY]. Số điện thoại của tôi là [PHONE] và email là [EMAIL]. ..." Trong ví dụ trên, prompt đã hướng dẫn rất chi tiết: cần làm gì (loại bỏ PII), cách làm (thay bằng placeholder trong ngoặc vuông, và cho ví dụ cụ thể các loại placeholder), và áp dụng trên nội dung email mẫu. Kết quả, mô hình dễ dàng thực hiện chính xác. Thú vị hơn, mô hình có thể suy ra những PII không được liệt kê rõ – chẳng hạn tự hiểu “ABC” là tên công ty và thay bằng [COMPANY], dù prompt không nhắc trực tiếp, nhờ ngữ cảnh đã cung cấp. Lưu ý khi dùng Instruction Prompting:

Chia nhỏ nhiệm vụ: Nếu công việc quá phức tạp, hãy hướng dẫn theo từng bước một. Bạn có thể yêu cầu AI thực hiện từng bước và kiểm tra kết quả trước khi sang bước tiếp. (Ví dụ: “Bước 1: tìm tất cả PII. Bước 2: thay thế PII…”).

Ngôn ngữ đơn nghĩa: Sử dụng câu ngắn gọn, tránh lối diễn đạt mập mờ hoặc hoa mỹ. Hãy viết prompt như thể bạn đang viết hướng dẫn sử dụng cho AI.

Kiểm tra và điều chỉnh: Đọc kỹ output, nếu AI chưa làm đúng mọi bước, hãy bổ sung/nhấn mạnh hướng dẫn trong prompt và thử lại.

Instruction prompting là một công cụ rất mạnh. Từ việc định dạng văn bản, xử lý dữ liệu (như ví dụ trên), cho đến những nhiệm vụ như đánh giá bài luận, phân tích văn bản – bạn đều có thể hướng dẫn AI làm theo cách mình muốn. Kỹ thuật này giúp “bẻ” những việc phức tạp thành hướng dẫn mà AI hiểu được, tiết kiệm thời gian và công sức so với làm thủ công hoặc lập trình truyền thống.

1. Role Prompting (Prompt dựa trên vai trò)

Role Prompting là kỹ thuật trong đó bạn gán cho AI một vai trò hoặc nhân vật cụ thể ngay trong prompt, nhằm kiểm soát phong cách và chất lượng câu trả lời. Hiểu nôm na, bạn đang yêu cầu AI “hãy giả làm X” – và tùy vai trò X, AI sẽ tự điều chỉnh giọng điệu, ngôn ngữ, mức độ chi tiết, thậm chí mức độ chính xác chuyên môn của phản hồi. Cách thực hiện rất đơn giản: thường bắt đầu prompt bằng cụm “Bạn là một [vai trò]…” hoặc “Hãy đóng vai [nhân vật]…”. Role có thể là nghề nghiệp (bác sĩ, luật sư, lập trình viên…), phong cách (một nhà thơ, người kể chuyện cổ tích, nhà phê bình khó tính…), hoặc thậm chí cụ thể tên người (giả lập văn phong của một tác giả nổi tiếng chẳng hạn). Tác dụng của Role Prompting:

Điều chỉnh phong cách/giọng điệu: Ví dụ, cùng là mô tả về một món ăn, nhưng vai “đầu bếp chuyên nghiệp” sẽ tả một cách tinh tế, dùng nhiều thuật ngữ ẩm thực; còn vai “nhà phê bình ẩm thực khó tính” có thể đưa ra nhận xét khắt khe hơn.

Nâng độ chính xác hoặc chiều sâu kiến thức: Khi bạn đặt vai trò “chuyên gia [lĩnh vực]”, mô hình sẽ ưu tiên sử dụng kiến thức chuyên ngành và kiểm chứng thông tin kỹ hơn, giảm bớt văn phong lan man. Ví dụ, “Bạn là một nhà toán học xuất sắc…” rồi đưa bài toán, AI sẽ cố gắng giải đúng và chi tiết, thay vì chỉ cho đáp số đơn thuần.

Định hướng cách trình bày: Vai trò “giáo sư đại học” có thể khiến câu trả lời mang tính học thuật, trích dẫn, còn vai “học sinh tiểu học” sẽ khiến câu trả lời đơn giản, dễ hiểu hơn.

Ví dụ 1: Thay đổi phong cách văn bản

Giả sử ta muốn AI viết đánh giá cho một nhà hàng. Hãy xem sự khác biệt:

Role Prompt 1: “Bạn là một nhà phê bình ẩm thực nổi tiếng của tạp chí, hãy viết đánh giá về nhà hàng La Vista.”

Kết quả: AI sẽ viết với giọng điệu uyên bác, có thể khen/chê cụ thể từng món, so sánh với chuẩn mực ẩm thực, ngôn từ trau chuốt.

Role Prompt 2: “Bạn là một thực khách trẻ tuổi chia sẻ trải nghiệm ăn uống vui vẻ tại nhà hàng La Vista trên blog cá nhân.”

Kết quả: Văn phong sẽ trẻ trung, thân thiện, tập trung vào cảm xúc trải nghiệm, có thể ít đi vào chi tiết kỹ thuật nấu nướng hơn so với vai nhà phê bình.

Như vậy, chỉ thay đổi vai trò, ta đã có hai kiểu review hoàn toàn khác nhau về cùng một nhà hàng. Ví dụ 2: Tăng độ chính xác cho tính toán

Bạn muốn AI giải một bài toán phức tạp. Trải nghiệm cho thấy nếu chỉ đưa biểu thức trần trụi, đôi khi AI (đặc biệt các mô hình cũ) có thể tính nhầm. Hãy thử:

Prompt thông thường: “100 \* 100 / 400 \* 56 = ?”

Có thể AI trả lời sai (280) do hiểu nhầm phép tính hoặc tính nhầm.

Role Prompt (Mathematician): “Bạn là một nhà toán học xuất sắc, có thể giải bất kỳ bài toán nào trên thế giới. Hãy thử giải bài toán sau: 100 \* 100 / 400 \* 56 = ?”

Kết quả: AI tính tuần tự và trả lời đúng: 1400.

Trong trường hợp này, việc gán vai “nhà toán học” đã “nhắc nhở” AI cẩn thận và tư duy toán học hơn, thay vì vội vàng đưa ra kết quả. (Dĩ nhiên với các mô hình mới như GPT-4, dù không gán vai, chúng cũng ít khi sai bài đơn giản. Nhưng với mô hình nhỏ hơn, vai trò có thể cải thiện kết quả.) Lưu ý khi sử dụng Role Prompting:

Lựa chọn vai trò phù hợp với mục đích. Nếu bạn muốn sự sáng tạo, có thể giao vai nghệ sĩ, nhà thơ; nếu muốn chính xác, giao vai chuyên gia lĩnh vực.

Không nên mâu thuẫn vai trò với nhiệm vụ. Ví dụ: “Bạn là nhà sử học, hãy viết mã Python…” – role này không hỗ trợ cho task code. Trừ phi bạn cố tình muốn văn phong lịch sử trong code (mà thường không).

Có thể kết hợp role + context: Ví dụ “Bạn là bác sĩ, dưới đây là bệnh án…” sẽ hiệu quả hơn là chỉ “Bạn là bác sĩ” rồi hỏi chẩn đoán mà không đưa thêm thông tin y khoa nào.

Role prompting được dùng rất linh hoạt: từ sáng tác, viết lách, giả lập hội thoại (đóng vai nhân vật X nói chuyện với Y) cho đến các ứng dụng nghiêm túc như hỗ trợ lập luận pháp lý (đóng vai luật sư) hay trợ giúp học tập (đóng vai giáo viên giải thích bài). Đây là một trong những kỹ thuật phổ biến nhất mà người dùng ChatGPT thường áp dụng một cách tự nhiên, có thể bạn đã dùng mà không để ý (ví dụ: “Hãy hành động như một chuyên gia…” chính là role prompt).

1. Prompting dựa trên Ví dụ: Zero-Shot, One-Shot, Few-Shot

Kỹ thuật thứ ba tận dụng việc chèn ví dụ minh họa vào prompt, như đã đề cập ở phần hướng dẫn mẹo. Chúng ta sẽ tìm hiểu chi tiết hơn về các khái niệm zero-shot, one-shot và few-shot prompting, thường được gọi chung là prompting dựa trên “shot” (In-Context Learning). Trước tiên, hiểu đơn giản: “shot” ám chỉ số lượng ví dụ mẫu được cung cấp trong prompt.

Zero-shot: Không cung cấp ví dụ nào, chỉ mô tả nhiệm vụ.

One-shot: Cung cấp một ví dụ mẫu (gồm đầu vào và đầu ra kỳ vọng).

Few-shot: Cung cấp nhiều ví dụ (thường là 2 đến 5 ví dụ) minh họa.

Mỗi phương pháp có ưu điểm riêng tùy tình huống, và nhìn chung, càng nhiều ví dụ phù hợp, mô hình càng hiểu rõ yêu cầu và cho kết quả chính xác hơn (cho đến một mức nào đó, vì quá nhiều sẽ vượt giới hạn hoặc gây nhiễu). Zero-Shot Prompting là gì?

Đây là cách thức cơ bản nhất: bạn chỉ cần đưa hướng dẫn hoặc câu hỏi trực tiếp, không đưa bất kỳ ví dụ nào. Mô hình sẽ phải dựa 100% vào kiến thức đã học từ dữ liệu huấn luyện để trả lời. Thú vị là, nhiều khi zero-shot cũng đủ dùng nếu nhiệm vụ đơn giản hoặc quen thuộc. Thực tế, các prompt dạng instruction hay role mà chúng ta thảo luận phía trên đều có thể xem là zero-shot (vì không có ví dụ mẫu, chỉ có hướng dẫn).

Ưu điểm: Ngắn gọn, tiết kiệm không gian prompt. Thích hợp cho những tác vụ mà mô hình đã “biết” (ví dụ hỏi kiến thức thông thường, định nghĩa, giải thích đơn giản).

Nhược điểm: Với nhiệm vụ phức tạp hoặc định dạng đầu ra đặc thù, zero-shot có thể khiến AI hiểu lầm yêu cầu hoặc tạo kết quả không đúng mong muốn, do thiếu mẫu để học theo trong ngữ cảnh.

Ví dụ zero-shot: Yêu cầu phân loại cảm xúc câu sau:

markdown

Sao chép

Chỉnh sửa

\*\*Prompt (Zero-shot):\*\* Phân loại cảm xúc của câu: "Tôi nghĩ kỳ nghỉ này ổn." thành \*\*tích cực, tiêu cực hoặc trung lập\*\*.

AI Output: “Trung lập.” Ở đây, mô hình dựa vào kinh nghiệm huấn luyện (có lẽ nó đã học về phân tích cảm xúc) để trả lời “Trung lập”. Zero-shot hoạt động tốt vì nhiệm vụ khá đơn giản. Nhưng hãy tưởng tượng một nhiệm vụ khó hơn, ví dụ phân tích văn phong văn học – nếu zero-shot, AI có thể lúng túng không biết bắt đầu từ đâu. One-Shot Prompting là gì?

One-shot cải thiện zero-shot bằng cách cung cấp một ví dụ duy nhất trước khi đưa ra nhiệm vụ chính. Ví dụ đó đóng vai trò minh họa cách chuyển từ đầu vào -> đầu ra. One-shot hữu ích khi bạn muốn kiểm tra xem chỉ một ví dụ đã đủ định hướng AI hay chưa. Ví dụ one-shot (tiếp nối ví dụ trên về cảm xúc):

markdown

Sao chép

Chỉnh sửa

\*\*Prompt (One-shot):\*\*

\*\*Ví dụ mẫu:\*\*

Văn bản: "Tôi yêu bộ phim này!"

Cảm xúc: Tích cực

\*\*Yêu cầu:\*\*

Văn bản: "Tôi nghĩ kỳ nghỉ này ổn."

Cảm xúc:

Trong prompt này, trước khi yêu cầu mô hình phân loại câu “Tôi nghĩ kỳ nghỉ này ổn”, ta đã cho nó thấy một ví dụ: câu “Tôi yêu bộ phim này!” -> cảm xúc “Tích cực”. Điều này giúp AI hiểu định dạng câu trả lời (chỉ cần nói loại cảm xúc) và biết rằng “ổn” có lẽ không tích cực hẳn, cũng không tiêu cực, nên nó sẽ trả lời “Trung lập” với độ tự tin cao hơn. One-shot thường đủ cho nhiệm vụ không quá phức tạp. Few-Shot Prompting là gì?

Few-shot là khi bạn cung cấp từ hai ví dụ trở lên. Đây là ứng dụng trực tiếp của In-Context Learning (ICL): mô hình học ngay từ các ví dụ trong ngữ cảnh prompt để áp dụng cho trường hợp mới. Thông thường, càng nhiều ví dụ đa dạng, mô hình càng nắm vững mẫu và cho kết quả tốt. Few-shot rất mạnh trong những trường hợp mà chỉ hướng dẫn thôi chưa đủ hoặc khi cần đầu ra tuân thủ một quy tắc nhất định. Chẳng hạn, hãy quay lại ví dụ chuyển đổi định dạng ngày tháng ở phần trước. Ta đã dùng two-shot (hai ví dụ) để mô hình hiểu quy tắc định dạng. Nếu chỉ nói “Hãy chuyển January 1, 2025 sang YYYY-MM-DD” (zero-shot), chưa chắc AI nhớ định dạng ISO là gì hoặc có thể nhầm lẫn. Nhưng với few-shot, độ chính xác tăng rõ rệt. Ví dụ few-shot khác: Giả sử chúng ta muốn AI dịch một câu tiếng Anh sang tiếng Việt theo văn phong trang trọng, ta có thể đưa 2 ví dụ dịch mẫu câu tương tự để đảm bảo văn phong đúng, rồi mới đưa câu cần dịch. So sánh nhanh Zero vs One vs Few:

Zero-shot: Phù hợp nhiệm vụ đơn giản, kiến thức phổ quát. Ví dụ: “Thủ đô của Pháp là gì?” – không cần ví dụ.

One-shot: Dùng khi cần gợi ý nhẹ về format hoặc logic. Ví dụ: phân loại văn bản ngắn, chuyển đổi đơn vị có một quy tắc.

Few-shot: Dùng cho nhiệm vụ phức tạp, đòi hỏi format nghiêm ngặt hoặc logic phức, hoặc khi zero-shot cho kết quả chưa tốt. Càng nhiều ví dụ, AI càng hiểu rõ yêu cầu (dĩ nhiên ví dụ phải đúng và đa dạng).

Lưu ý: Few-shot tuy mạnh nhưng cũng có giới hạn: bạn không thể cung cấp quá nhiều ví dụ vì prompt có độ dài giới hạn (tùy mô hình). Thường 3-5 ví dụ chất lượng là đủ cho AI học mẫu. Ngoài ra, nếu ví dụ không sát với trường hợp thực, AI có thể bị “nhiễu” – nên chọn ví dụ tiêu biểu.

Kết hợp các kỹ thuật

Ba kỹ thuật trên không loại trừ nhau, ngược lại có thể kết hợp trong cùng một prompt phức tạp. Ví dụ, bạn có thể viết một instruction prompt dài gồm nhiều bước, trong đó bạn cũng gán role cho AI và kèm ví dụ minh họa ở một bước nào đó. Một prompt cao cấp có thể trông như:

“Bạn là chuyên gia X... (role). Dưới đây là dữ liệu Y... (context). Hãy thực hiện các bước sau: 1)... 2)... (instruction). Ví dụ: ... (one-shot example). Cuối cùng, xuất kết quả theo format Z (format).”

Kết hợp linh hoạt giúp tailor prompt đúng theo nhu cầu đa dạng của các tình huống thực tế.

Kết luận: Từ “mơ hồ” đến “pro” trong tương tác với AI

Qua các phần trên, chúng ta đã tóm lược những nội dung cốt lõi của “Prompt Engineering – Từ Mơ hồ thành Pro”:

Hiểu về AI và Generative AI: Nền tảng để biết chúng ta đang làm việc với hệ thống thông minh ra sao, sức mạnh và giới hạn của chúng.

Nắm vững Prompt Engineering: Biết được tầm quan trọng của việc viết prompt, cách một prompt tốt có thể “dẫn dắt” AI tạo ra kết quả vượt trội.

Các mẹo viết prompt hiệu quả: Tính cụ thể, cấu trúc, ngữ cảnh, ví dụ, và tinh chỉnh – giúp biến những yêu cầu mơ hồ ban đầu thành hướng dẫn rành mạch cho AI.

Cấu trúc và thành phần prompt: Hiểu rõ từng mảnh ghép (Task, Context, Examples, Role, Format) để lắp ghép thành prompt hoàn chỉnh, cũng như trình tự sắp xếp chúng thông minh.

Các kỹ thuật prompting nâng cao: Từ Instruction Prompting (hướng dẫn tuần tự chi tiết), Role Prompting (nhập vai để định hướng phong cách/độ chính xác), đến Zero/One/Few-Shot Prompting (cung cấp ví dụ minh họa để tăng hiệu quả học trong ngữ cảnh). Mỗi kỹ thuật đều có ví dụ minh họa cụ thể, giúp người đọc hình dung áp dụng vào trường hợp thực tế.

Với những kiến thức này, người mới bắt đầu có thể mạnh dạn thử nghiệm và dần dần cải thiện kỹ năng viết prompt. Người đã có kinh nghiệm cũng có thể hệ thống hóa lại hiểu biết và khám phá thêm kỹ thuật mới (hoặc kết hợp các kỹ thuật) để giải quyết những bài toán khó hơn. Ứng dụng thực tế: Prompt Engineering không chỉ dùng cho ChatGPT. Bạn có thể áp dụng nguyên tắc tương tự khi làm việc với bất kỳ mô hình generative AI nào: viết lời miêu tả cho Midjourney/DALL-E để vẽ tranh theo ý muốn, gõ lệnh cho GitHub Copilot để gợi ý mã, hay hướng dẫn Claude tóm tắt tài liệu dài… Dù nền tảng nào, tư duy “ra đề” cho AI vẫn dựa trên cách bạn cấu trúc và diễn đạt prompt. Lời khuyên cuối: Hãy luyện tập thường xuyên. Mỗi lần bạn tinh chỉnh prompt và thấy kết quả cải thiện, đó là một bước tiến từ “mơ hồ” đến “pro”. Dần dần, viết prompt hay sẽ trở thành bản năng thứ hai của bạn khi làm việc với AI. Và với một prompt “pro” trong tay, bạn có thể khai thác tối đa sức mạnh của generative AI, phục vụ cho công việc và cuộc sống một cách sáng tạo và hiệu quả.
