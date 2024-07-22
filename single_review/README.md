# Một review

## Liệt kê các khía cạnh của sản phẩm

Prompt:
```
Liệt kê ra các khía cạnh đánh giá về sản phẩm "Tai nghe Sennheiser Momentum 4 Wireless Denim" mà người mua hàng trên các trang thương mại điện tử  thường quan tâm, các khía cạnh cơ bản cần có: Giá cả, Đóng gói sản phẩm, Dịch vụ giao hàng, Chất lượng sản phẩm, Dịch vụ đổi trả. Thêm vài khía cạnh thường có nữa, không thêm khía cạnh Đánh giá của những người dùng khác

Trả lời dạng array

Trả lời:
```

Ans:
```
[
    "Giá cả",
    "Đóng gói sản phẩm",
    "Dịch vụ giao hàng",
    "Chất lượng sản phẩm",
    "Dịch vụ đổi trả",
    "Thời gian sử dụng pin",
    "Chất lượng âm thanh",
    "Thiết kế và sự thoải mái",
    "Tính năng chống ồn",
    "Khả năng kết nối và tương thích",
    "Độ bền và chất lượng xây dựng"
]
```

## Đánh giá sản phẩm

Prompt:
```
Đánh giá xem bình luận sau đây là Tích cực, Tiêu cực hay Trung lập.
"Đóng hộp hơi bị méo mó nhưng It nhất tai nghe vẫn dùng tốt. Giá hơi cao quá"

Sau đó, dựa trên các khía cạnh vừa liệt kê, đánh giá các khía cạnh đó trong bình luận. Nếu bình luận không đề cập tới khía cạnh đó, trả lời là "Không đề cập". Nếu trong bình luận có khía cạnh không xuất hiện trong danh sách trên, tự động thêm khía cạnh đó vào và đánh giá, không được bỏ qua khía cạnh nào. Mỗi khía cạnh có 2 trường, đầu tiên quan điểm là "Tích cực", "Tiêu cực"  hoặc "Trung lập", trường thứ 2 là đoạn nói lên quan điểm đó. Trả lời dạng json với format sau

{
    "review": "Nội dung bình luận",
    "overall-opinion": "Tích cực, Tiêu cực hoặc Trung lập",
    "aspects": [
        {
            "aspect": "Khía cạnh",
            "opinion": "Tích cực, Tiêu cực hoặc Trung lập",
            "detail": "Đoạn nói về khía cạnh này"
        }
    ]
}

Trả lời:
```

Ans:
```
{
    "review": "Đóng hộp hơi bị méo mó nhưng It nhất tai nghe vẫn dùng tốt. Giá hơi cao quá",
    "overall-opinion": "Trung lập",
    "aspects": [
        {
            "aspect": "Giá cả",
            "opinion": "Tiêu cực",
            "detail": "Giá hơi cao quá"
        },
        {
            "aspect": "Đóng gói sản phẩm",
            "opinion": "Tiêu cực",
            "detail": "Đóng hộp hơi bị méo mó"
        },
        {
            "aspect": "Dịch vụ giao hàng",
            "opinion": "Không đề cập",
            "detail": "Không đề cập"
        },
        {
            "aspect": "Chất lượng sản phẩm",
            "opinion": "Tích cực",
            "detail": "Tai nghe vẫn dùng tốt"
        },
        {
            "aspect": "Dịch vụ đổi trả",
            "opinion": "Không đề cập",
            "detail": "Không đề cập"
        },
        {
            "aspect": "Thời gian sử dụng pin",
            "opinion": "Không đề cập",
            "detail": "Không đề cập"
        },
        {
            "aspect": "Chất lượng âm thanh",
            "opinion": "Không đề cập",
            "detail": "Không đề cập"
        },
        {
            "aspect": "Thiết kế và sự thoải mái",
            "opinion": "Không đề cập",
            "detail": "Không đề cập"
        },
        {
            "aspect": "Tính năng chống ồn",
            "opinion": "Không đề cập",
            "detail": "Không đề cập"
        },
        {
            "aspect": "Khả năng kết nối và tương thích",
            "opinion": "Không đề cập",
            "detail": "Không đề cập"
        },
        {
            "aspect": "Độ bền và chất lượng xây dựng",
            "opinion": "Không đề cập",
            "detail": "Không đề cập"
        }
    ]
}
```
