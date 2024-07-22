# Một review

## Liệt kê các khía cạnh của sản phẩm

Prompt:
```
Liệt kê ra các khía cạnh đánh giá về sản phẩm "Hiểu Chồng Để Làm Người Vợ Tốt" mà người mua hàng trên các trang thương mại điện tử thường quan tâm, các khía cạnh cơ bản cần có: Giá cả, Đóng gói sản phẩm, Dịch vụ giao hàng, Chất lượng sản phẩm, Dịch vụ đổi trả. Thêm vài khía cạnh thường có nữa, không thêm khía cạnh Đánh giá của những người dùng khác

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
    "Mô tả sản phẩm",
    "Thời gian sử dụng",
    "Thiết kế và hình thức",
    "Tính ứng dụng và giá trị nội dung",
    "Hỗ trợ khách hàng",
    "Độ tin cậy của nhà cung cấp"
]
```

## Đánh giá sản phẩm
### Prompt 1
Prompt:
```
Đánh giá xem các bình luận sau đây là Tích cực, Tiêu cực hay Trung lập.
[
    "Giao hàng đúng hẹn , sách hay ,1 cuốn có cd ,1 cuốn ko có cd , mình nghe bằng qr nên cũng không sao , Đóng hàng sơ sài bị rách , bẹp , nhân viên giao hàng Tiki không thân thiện lắm .",
    "Mua sách ở tiki thì hiếm khi nào cảm thấy không hài lòng, giá lại tốt hơn bên ngoài rất nhiều. Đóng gói và giao hàng ổn.",
    "Nội dung sách không thú vị.",
    "Sách thì ok nhưng không hiểu sao đĩa CD thì cuốn có cuốn không có? Mình không xài nên cũng không muốn đổi, nhưng liệu sách có chính hãng k ạ?",
    "Chê trước rồi khen sau !!!!!
    Chán chả buồn nói khi mua sách của nhà xuất bản có tem hẳn hòi mà vẫn bị lỗi dán gáy sách, đọc đến trang 176 thì buồn vô cùng, sách đọc để nghiên cứu còn phải đọc đi đọc lại mà mới lần 1 mà tơi bời hoa lá cành thế này thì nhà xuất bản phải xem lại 
    Ngoài ra thì nội dung sách khỏi phải bàn vì quá tuyệt vời, thẩm mỹ đẹp
    Chỉ vì bị dị ứng với sách rớt gáy mà mất hẳn 2 sao thì nhà phân phối sách nên phản ảnh lại với công ty xuất bản nhé",
    "Bộ sách tuyệt vời không chỉ giành riêng cho vợ chồng. Sách mình mua tặng, đóng gói đẹp."
]

Sau đó, dựa trên các khía cạnh vừa liệt kê, phân tích chi tiết các khía cạnh được nhắc tới trong các bình luận, không được bỏ sót.
Các đoạn nhỏ về các khía cạnh trong các bình luận đều cần được phân tích và cho vào khía cạnh tương ứng, nếu không có khía cạnh đó trong danh sách trên thì tự động tạo mới. Không được bỏ sót bất kì đoạn nhỏ nào nói về khía cạnh.
Một bình luận chỉ được xuất hiện tại 1 trong 3 mục positive, negative hoặc neutral.
Trả lời dạng json với format sau

{
    "positive": [
        "Các bình luận tích cực (bình luận đầy đủ, không cắt bớt)"
    ],
    "negative": [
        "Các bình luận tiêu cực (bình luận đầy đủ, không cắt bớt)"
    ],
    "neutral": [
        "Các bình luận trung lập (bình luận đầy đủ, không cắt bớt)"
    ],
    "aspects": [
        {
            "aspect": "Khía cạnh",
            "opinion": {
                "Tích cực": [
                    "Các đoạn ngắn chính xác về tích cực của khía cạnh này trong các bình luận, không phải cả bình luận"
                ],
                "Tiêu cực": [
                    "Các đoạn ngắn chính xác về tiêu cực của khía cạnh này trong các bình luận, không phải cả bình luận"
                ],
                "Trung lập":[
                    "Các đoạn ngắn chính xác về trung lập của khía cạnh này trong các bình luận, không phải cả bình luận"
                ],
            }
        }
    ]
}

Trả lời:
```

Ans:
```
{
    "positive": [
        "Mua sách ở tiki thì hiếm khi nào cảm thấy không hài lòng, giá lại tốt hơn bên ngoài rất nhiều. Đóng gói và giao hàng ổn.",
        "Bộ sách tuyệt vời không chỉ giành riêng cho vợ chồng. Sách mình mua tặng, đóng gói đẹp."
    ],
    "negative": [
        "Giao hàng đúng hẹn , sách hay ,1 cuốn có cd ,1 cuốn ko có cd , mình nghe bằng qr nên cũng không sao , Đóng hàng sơ sài bị rách , bẹp , nhân viên giao hàng Tiki không thân thiện lắm .",
        "Nội dung sách không thú vị.",
        "Chê trước rồi khen sau !!!! Chán chả buồn nói khi mua sách của nhà xuất bản có tem hẳn hòi mà vẫn bị lỗi dán gáy sách, đọc đến trang 176 thì buồn vô cùng, sách đọc để nghiên cứu còn phải đọc đi đọc lại mà mới lần 1 mà tơi bời hoa lá cành thế này thì nhà xuất bản phải xem lại Ngoài ra thì nội dung sách khỏi phải bàn vì quá tuyệt vời, thẩm mỹ đẹp Chỉ vì bị dị ứng với sách rớt gáy mà mất hẳn 2 sao thì nhà phân phối sách nên phản ảnh lại với công ty xuất bản nhé"
    ],
    "neutral": [
        "Sách thì ok nhưng không hiểu sao đĩa CD thì cuốn có cuốn không có? Mình không xài nên cũng không muốn đổi, nhưng liệu sách có chính hãng k ạ?"
    ],
    "aspects": [
        {
            "aspect": "Giá cả",
            "opinion": {
                "Tích cực": [
                    "Giá lại tốt hơn bên ngoài rất nhiều."
                ],
                "Tiêu cực": [],
                "Trung lập": []
            }
        },
        {
            "aspect": "Đóng gói sản phẩm",
            "opinion": {
                "Tích cực": [
                    "Đóng gói đẹp."
                ],
                "Tiêu cực": [
                    "Đóng hàng sơ sài bị rách , bẹp."
                ],
                "Trung lập": []
            }
        },
        {
            "aspect": "Dịch vụ giao hàng",
            "opinion": {
                "Tích cực": [],
                "Tiêu cực": [
                    "Nhân viên giao hàng Tiki không thân thiện lắm."
                ],
                "Trung lập": []
            }
        },
        {
            "aspect": "Chất lượng sản phẩm",
            "opinion": {
                "Tích cực": [
                    "Sách tuyệt vời không chỉ giành riêng cho vợ chồng."
                ],
                "Tiêu cực": [
                    "Nội dung sách không thú vị.",
                    "Lỗi dán gáy sách, đọc đến trang 176 thì tơi bời hoa lá cành."
                ],
                "Trung lập": [
                    "Sách thì ok nhưng không hiểu sao đĩa CD thì cuốn có cuốn không có?"
                ]
            }
        },
        {
            "aspect": "Dịch vụ đổi trả",
            "opinion": {
                "Tích cực": [],
                "Tiêu cực": [],
                "Trung lập": []
            }
        },
        {
            "aspect": "Mô tả sản phẩm",
            "opinion": {
                "Tích cực": [],
                "Tiêu cực": [],
                "Trung lập": [
                    "Sách thì ok nhưng không hiểu sao đĩa CD thì cuốn có cuốn không có?"
                ]
            }
        },
        {
            "aspect": "Thời gian sử dụng",
            "opinion": {
                "Tích cực": [],
                "Tiêu cực": [],
                "Trung lập": []
            }
        },
        {
            "aspect": "Thiết kế và hình thức",
            "opinion": {
                "Tích cực": [
                    "Thẩm mỹ đẹp."
                ],
                "Tiêu cực": [],
                "Trung lập": []
            }
        },
        {
            "aspect": "Tính ứng dụng và giá trị nội dung",
            "opinion": {
                "Tích cực": [
                    "Nội dung sách khỏi phải bàn vì quá tuyệt vời."
                ],
                "Tiêu cực": [],
                "Trung lập": []
            }
        },
        {
            "aspect": "Hỗ trợ khách hàng",
            "opinion": {
                "Tích cực": [],
                "Tiêu cực": [],
                "Trung lập": []
            }
        },
        {
            "aspect": "Độ tin cậy của nhà cung cấp",
            "opinion": {
                "Tích cực": [],
                "Tiêu cực": [],
                "Trung lập": []
            }
        }
    ]
}
```

### Prompt 2
Prompt:
```
Đánh giá xem các bình luận sau đây là Tích cực, Tiêu cực hay Trung lập.
[
    "Giao hàng đúng hẹn , sách hay ,1 cuốn có cd ,1 cuốn ko có cd , mình nghe bằng qr nên cũng không sao , Đóng hàng sơ sài bị rách , bẹp , nhân viên giao hàng Tiki không thân thiện lắm .",
    "Mua sách ở tiki thì hiếm khi nào cảm thấy không hài lòng, giá lại tốt hơn bên ngoài rất nhiều. Đóng gói và giao hàng ổn.",
    "Nội dung sách không thú vị.",
    "Sách thì ok nhưng không hiểu sao đĩa CD thì cuốn có cuốn không có? Mình không xài nên cũng không muốn đổi, nhưng liệu sách có chính hãng k ạ?",
    "Chê trước rồi khen sau !!!!!
    Chán chả buồn nói khi mua sách của nhà xuất bản có tem hẳn hòi mà vẫn bị lỗi dán gáy sách, đọc đến trang 176 thì buồn vô cùng, sách đọc để nghiên cứu còn phải đọc đi đọc lại mà mới lần 1 mà tơi bời hoa lá cành thế này thì nhà xuất bản phải xem lại 
    Ngoài ra thì nội dung sách khỏi phải bàn vì quá tuyệt vời, thẩm mỹ đẹp
    Chỉ vì bị dị ứng với sách rớt gáy mà mất hẳn 2 sao thì nhà phân phối sách nên phản ảnh lại với công ty xuất bản nhé",
    "Bộ sách tuyệt vời không chỉ giành riêng cho vợ chồng. Sách mình mua tặng, đóng gói đẹp."
]

Sau đó, dựa trên các khía cạnh vừa liệt kê, phân tích chi tiết các khía cạnh được nhắc tới trong các bình luận, không được bỏ sót.
Các đoạn nhỏ về các khía cạnh trong các bình luận đều cần được phân tích và cho vào khía cạnh tương ứng, nếu không có khía cạnh đó trong danh sách trên thì tự động tạo mới. Không được bỏ sót bất kì đoạn nhỏ nào nói về khía cạnh.
Nếu không có đoạn nào trong bình luận đề cập tới một khía cạnh trong danh sách trên, bỏ qua. Các đoạn về 1 khía cạnh chứa trong cùng 1 phần tử, không tạo phần tử mới có trùng khía cạnh
Trả lời dạng json với format sau

[
    {
        "review": "Nội dung bình luận",
        "overall-opinion": "Tích cực, Tiêu cực hoặc Trung lập",
        "aspects": [
            {
                "aspect": "Khía cạnh",
                "opinion": "Tích cực, Tiêu cực hoặc Trung lập",
                "detail": {
                    "positive": "Đoạn nói về mặt tích cực, nếu không có thì bỏ trường này",
                    "negative": "Đoạn nói về mặt tiêu cực, nếu không có thì bỏ trường này",
                    "neutral": "Đoạn nói về mặt trung lập, nếu không có thì bỏ trường này",
                }
            }
        ]
    }
]

Trả lời:
```

Ans:
```
[
    {
        "review": "Giao hàng đúng hẹn , sách hay ,1 cuốn có cd ,1 cuốn ko có cd , mình nghe bằng qr nên cũng không sao , Đóng hàng sơ sài bị rách , bẹp , nhân viên giao hàng Tiki không thân thiện lắm .",
        "overall-opinion": "Trung lập",
        "aspects": [
            {
                "aspect": "Dịch vụ giao hàng",
                "opinion": "Tiêu cực",
                "detail": {
                    "negative": "Nhân viên giao hàng Tiki không thân thiện lắm",
                }
            },
            {
                "aspect": "Đóng gói sản phẩm",
                "opinion": "Tiêu cực",
                "detail": {
                    "negative": "Đóng hàng sơ sài bị rách, bẹp"
                }
            },
            {
                "aspect": "Chất lượng sản phẩm",
                "opinion": "Trung lập",
                "detail": {
                    "neutral": "1 cuốn có CD, 1 cuốn không có CD, mình nghe bằng QR nên cũng không sao"
                }
            }
        ]
    },
    {
        "review": "Mua sách ở tiki thì hiếm khi nào cảm thấy không hài lòng, giá lại tốt hơn bên ngoài rất nhiều. Đóng gói và giao hàng ổn.",
        "overall-opinion": "Tích cực",
        "aspects": [
            {
                "aspect": "Giá cả",
                "opinion": "Tích cực",
                "detail": {
                    "positive": "Giá lại tốt hơn bên ngoài rất nhiều"
                }
            },
            {
                "aspect": "Đóng gói sản phẩm",
                "opinion": "Tích cực",
                "detail": {
                    "positive": "Đóng gói ổn"
                }
            },
            {
                "aspect": "Dịch vụ giao hàng",
                "opinion": "Tích cực",
                "detail": {
                    "positive": "Giao hàng ổn"
                }
            }
        ]
    },
    {
        "review": "Nội dung sách không thú vị.",
        "overall-opinion": "Tiêu cực",
        "aspects": [
            {
                "aspect": "Tính năng và nội dung",
                "opinion": "Tiêu cực",
                "detail": {
                    "negative": "Nội dung sách không thú vị"
                }
            }
        ]
    },
    {
        "review": "Sách thì ok nhưng không hiểu sao đĩa CD thì cuốn có cuốn không có? Mình không xài nên cũng không muốn đổi, nhưng liệu sách có chính hãng k ạ?",
        "overall-opinion": "Trung lập",
        "aspects": [
            {
                "aspect": "Chất lượng sản phẩm",
                "opinion": "Trung lập",
                "detail": {
                    "neutral": "Sách thì ok nhưng không hiểu sao đĩa CD thì cuốn có cuốn không có"
                }
            },
            {
                "aspect": "Thông tin sản phẩm",
                "opinion": "Trung lập",
                "detail": {
                    "neutral": "Liệu sách có chính hãng không"
                }
            }
        ]
    },
    {
        "review": "Chê trước rồi khen sau !!!!! Chán chả buồn nói khi mua sách của nhà xuất bản có tem hẳn hòi mà vẫn bị lỗi dán gáy sách, đọc đến trang 176 thì buồn vô cùng, sách đọc để nghiên cứu còn phải đọc đi đọc lại mà mới lần 1 mà tơi bời hoa lá cành thế này thì nhà xuất bản phải xem lại Ngoài ra thì nội dung sách khỏi phải bàn vì quá tuyệt vời, thẩm mỹ đẹp Chỉ vì bị dị ứng với sách rớt gáy mà mất hẳn 2 sao thì nhà phân phối sách nên phản ảnh lại với công ty xuất bản nhé",
        "overall-opinion": "Trung lập",
        "aspects": [
            {
                "aspect": "Chất lượng sản phẩm",
                "opinion": "Tiêu cực",
                "detail": {
                    "negative": "Lỗi dán gáy sách, sách bị tơi bời, không được như mong đợi khi nghiên cứu"
                }
            },
            {
                "aspect": "Tính chính xác của mô tả sản phẩm",
                "opinion": "Tiêu cực",
                "detail": {
                    "negative": "Nhà xuất bản có tem hẳn hòi nhưng vẫn bị lỗi dán gáy sách"
                }
            },
            {
                "aspect": "Tính năng và nội dung",
                "opinion": "Tích cực",
                "detail": {
                    "positive": "Nội dung sách khỏi phải bàn vì quá tuyệt vời"
                }
            },
            {
                "aspect": "Thẩm mỹ",
                "opinion": "Tích cực",
                "detail": {
                    "positive": "Thẩm mỹ đẹp"
                }
            }
        ]
    },
    {
        "review": "Bộ sách tuyệt vời không chỉ giành riêng cho vợ chồng. Sách mình mua tặng, đóng gói đẹp.",
        "overall-opinion": "Tích cực",
        "aspects": [
            {
                "aspect": "Chất lượng sản phẩm",
                "opinion": "Tích cực",
                "detail": {
                    "positive": "Bộ sách tuyệt vời không chỉ giành riêng cho vợ chồng"
                }
            },
            {
                "aspect": "Đóng gói sản phẩm",
                "opinion": "Tích cực",
                "detail": {
                    "positive": "Đóng gói đẹp"
                }
            }
        ]
    }
]
```
