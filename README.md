# ⚓ Hải Chiến (Battleship)

Game **bắn tàu** cho 2 người, chơi ngay trên trình duyệt: bố trí hạm đội bí mật, rồi lần lượt khai hỏa vào vùng biển địch. Ai đánh chìm toàn bộ hạm đội đối phương trước sẽ thắng.

## Chế độ chơi
- **Chơi với máy**: nhập tên, bấm *Chơi với máy*. Có 3 mức: Dễ (bắn ngẫu nhiên), Vừa (săn theo ô cờ + bám mục tiêu), Khó (bản đồ mật độ xác suất).
- **Online 1 đấu 1**: bấm *Tạo phòng*, gửi mã hoặc link cho bạn bè; bạn bè nhập mã và bấm *Vào phòng*.
  Người tạo phòng phải **giữ tab mở**, vì máy chủ phòng giữ trạng thái ván chơi.

## Luật
- Hải đồ 10×10 (A–J, 1–10). Hạm đội: Tàu sân bay (5), Thiết giáp hạm (4), Tuần dương hạm (3), Tàu ngầm (3), Khu trục hạm (2).
- Đặt tàu ngang hoặc dọc, không chồng nhau. Tùy chọn: *tàu không được đặt sát nhau* (kể cả chéo).
- Luật bắn (chọn khi tạo phòng):
  - **Cổ điển**: mỗi lượt 1 phát.
  - **Trúng bắn tiếp**: trúng thì bắn tiếp, trượt mới mất lượt.
  - **Salvo**: mỗi lượt bắn số phát bằng số tàu mình còn nổi.
- Tàu chìm khi mọi ô của nó bị trúng, và sẽ lộ nguyên hình trên hải đồ địch.

## Điều khiển
- Bố trí: bấm tên tàu rồi bấm lên hải đồ; bấm vào tàu đã đặt để nhấc lên. Xoay bằng nút ⟳, phím **R** hoặc chuột phải. Có nút *Ngẫu nhiên*.
- Khai hỏa: bấm một ô trên vùng biển địch. Trên điện thoại chạm 1 lần để ngắm, chạm lần nữa để bắn.
- Salvo: chọn đủ mục tiêu rồi bấm *Khai hỏa* (hoặc Enter).

## Kỹ thuật
Một file `index.html` duy nhất, đồ họa vẽ hoàn toàn bằng CSS + SVG (mặt nước động, radar quét, tàu vẽ tay, lửa/khói, nổ và cột nước), âm thanh tổng hợp bằng Web Audio.
Kết nối P2P bằng [PeerJS](https://peerjs.com/), cùng khung với Quoridor, Azul, Jaipur. Máy chủ phòng chỉ gửi cho mỗi người vị trí tàu của chính họ và các tàu địch đã chìm.
Chạy thử: `npx http-server battleship -p 5192`.
