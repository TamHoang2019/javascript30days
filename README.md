# javascript30days
01. Make a JavaScript Drum Kit in Vanilla JS!
**CSS
 - Sử dụng flex cho div cha div.keys, căn giữa các element bên trong theo chiều ngang-chiều dọc.
 - Sử dụng background cho html.
 - Tạo root font-size tức là css font-size cho thẻ body theo đơn vị pixel: 10pixel.
 => 1 rem = 10pixel. 
 => các đơn vị tính trở về sau sẽ sử dụng theo rem.
**JS
- Cho object window lắng nghe sự kiện nhấn phím (keydown), lấy được keyCode thông qua tham số event.
- Truyền event này vào function callback xử lý các tác vụ:
 - Sử dụng querySelector để lấy ra DOM audio có thuộc tính [data-key=event.keyCode].
 - Sử dụng template string: audio[`data-key="${event.keyCode}"`] 
 - Nếu DOM lấy ra là có (vì có khả năng ngừoi dùng nhấn các phím ngoài dãy phím A S D F G H J K L), thì gọi method play cho DOM vừa lấy ra được: audio.play()
- Xử lý trường hợp: user nhấn liên tục 1 phím, theo đúng trải nghiệm thì phải play lại audio đó, chứ không đợi cho audio trước chạy xong thì mới play audio vừa mới nhấn sau đó.
 + Trước khi gọi method audio.play(), ta set property audio.currentTime = 0
 + Property currentTime của 1 object audio hoặc video sẽ giúp lấy ra hoặc cài đặt vào thời điểm (theo giây) chạy của audio hoặc video đó. (xem thêm: https://www.w3schools.com/tags/av_prop_currenttime.asp)