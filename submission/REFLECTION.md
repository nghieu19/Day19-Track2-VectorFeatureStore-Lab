# Reflection — Lab 19

**Tên:** Nguyễn Thị Hiểu
**Cohort:** A20-K2
**Path đã chạy:** lite

---

## Câu hỏi (≤ 200 chữ)

> Trên golden set 50 queries, mode nào thắng ở loại query nào (`exact` /
> `paraphrase` / `mixed`), và tại sao? Khi nào bạn **không** dùng hybrid
> (i.e. khi nào pure BM25 hoặc pure vector là lựa chọn đúng)?

- **BM25 (Keyword)** thắng hoặc ngang bằng ở câu hỏi `exact` vì thuật toán này bắt chính xác các từ vựng kỹ thuật xuất hiện trong văn bản.
- **Vector (Semantic)** về lý thuyết mạnh nhất ở câu hỏi `paraphrase` vì nó hiểu ngữ nghĩa dù không trùng từ khóa (tuy ở bài này dùng model tiếng Anh nên kết quả chưa thật sự cao).
- **Hybrid** thắng áp đảo ở loại `mixed` (loại phổ biến nhất trong thực tế) vì kết hợp được cả khả năng khớp từ khóa chính xác của BM25 và sự hiểu ngữ nghĩa của Vector thông qua thuật toán RRF.

**Khi nào KHÔNG dùng hybrid:**
- Khi hệ thống chỉ cần tìm mã lỗi (error codes), mã sản phẩm, hoặc mã định danh chính xác (lúc này pure BM25 là lựa chọn đúng vì nó nhanh, rẻ và không suy diễn sai lệch).

---

## Điều ngạc nhiên nhất khi làm lab này

Em khá bất ngờ khi thấy thuật toán Hybrid Search kết hợp RRF lại mang lại điểm Precision@10 tốt và toàn diện hơn hẳn so với khi chỉ dùng Vector hay Keyword riêng lẻ trên một tập văn bản thực tế.

---

## Bonus challenge

- [ ] Đã làm bonus (xem `bonus/`)
- [ ] Pair work với: _<tên đồng đội nếu có>_
