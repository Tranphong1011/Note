- Inline: 
	-Các phần tử Inline ko bao h bắt đầu 1 hàng mới
	-Chiếm width khi cần thiết , Nếu các items vượt quá độ dài của dòng thì item sẽ xuống dòng mới

	-Các item có kiểu display này **không thể set width và height**, width và height = content
	-Không thể set width và height
	-chỉ có thể điều chỉnh margin và padding **left and right** (top và bottom thì không thể).

Các inline elements như: ![](https://i.imgur.com/1rojuiF.png)

- Block:
	-luôn bắt đầu 1 hàng mới
	-Chiếm width càng nhiều càng tốt,chiếm toàn bộ width nếu width ko đc set, stretches out to the left and right as far as it can
	-set được width, height, margin, padding đầy đủ 4 hướng (top, bottom, right, left).
	-có thể add margin
	-có width là 100% parent width
	![](https://i.imgur.com/VfiAbRd.png)

- Inline-block 
-được sắp xếp giống với kiểu `display: inline`, nghĩa là các items sẽ được xếp cùng nhau trên một dòng
-có thuộc tính của `display: block` như là có set width, height, margin, padding đủ 4 hướng.