# H-c-t-p-
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>FO4 × CLB Ninh Bình United - Hoàn Chỉnh</title>
    <style>
        *{margin:0;padding:0;box-sizing:border-box;font-family:'Segoe UI',Roboto,sans-serif;}
        :root{--xanh:#0f5132;--vang:#ffc107;--do:#dc3545;--tim:#9333ea;--xanh-sam:#072c1e;--dong:#cd7f32;--bac:#c0c0c0;--cam:#ff6b00;}
        body{background:linear-gradient(180deg,var(--xanh-sam) 0%,var(--xanh) 50%,var(--xanh-sam) 100%);min-height:100vh;color:white;padding:12px;overflow-x:hidden;}

        /* INTRO + THANH TẢI */
        #introGame{position:fixed;inset:0;background:#000;z-index:9999;display:flex;flex-direction:column;align-items:center;justify-content:center;padding:30px;}
        .logo-ea{font-size:52px;font-weight:900;color:#fff;animation:zoomIn 1.2s ease-out;margin-bottom:20px;}
        @keyframes zoomIn{0%{transform:scale(2);opacity:0;}100%{transform:scale(1);opacity:1;}}
        .slogan{font-size:18px;color:var(--vang);letter-spacing:2px;margin-bottom:50px;opacity:0;animation:fadeIn 1s 1.5s forwards;}
        @keyframes fadeIn{to{opacity:1;}}
        .khoang-tai{width:100%;max-width:450px;}
        .thong-tin-tai{display:flex;justify-content:space-between;font-size:13px;color:#aaa;margin-bottom:8px;}
        .thanh-tai{width:100%;height:14px;background:#222;border-radius:7px;overflow:hidden;border:1px solid #444;}
        .do-tai{height:100%;width:0%;background:linear-gradient(90deg,#ffc107,#ffda6a);border-radius:7px;transition:width 0.1s ease;box-shadow:0 0 10px rgba(255,193,7,0.4);}
        .man-chuyen{position:absolute;inset:0;background:#fff;animation:chuyenMan 0.8s 5.5s forwards;}
        @keyframes chuyenMan{to{opacity:0;visibility:hidden;}}

        /* HIỆU ỨNG MỞ THẺ */
        #manMoThe{position:fixed;inset:0;background:rgba(0,0,0,0.95);z-index:9990;display:none;flex-direction:column;align-items:center;justify-content:center;}
        .hop-mo{font-size:100px;animation:xoayHop 1.5s ease-in-out;filter:drop-shadow(0 0 40px var(--vang));}
        @keyframes xoayHop{0%{transform:rotateY(0) scale(0.5);}50%{transform:rotateY(180deg) scale(1.2);}100%{transform:rotateY(360deg) scale(1);}}
        .tia-sang{position:absolute;width:100%;height:100%;background:radial-gradient(circle, rgba(255,193,7,0.4) 0%, transparent 60%);animation:quaySang 2s forwards;opacity:0;}
        @keyframes quaySang{0%{opacity:0;transform:scale(0.5);}50%{opacity:1;transform:scale(1.5);}100%{opacity:0;transform:scale(2);}}
        .kq-the{margin-top:30px;transform:translateY(100px) rotateY(180deg) scale(0);opacity:0;transition:all 0.8s 0.5s ease-out;}
        .hien-the-xong{transform:translateY(0) rotateY(0) scale(1);opacity:1;}
        .ten-dac-biet{font-size:28px;font-weight:900;color:var(--vang);margin-top:20px;animation:noiBat 1s 1.2s both;text-shadow:0 0 20px var(--vang);}
        @keyframes noiBat{from{opacity:0;transform:scaleX(0);}to{opacity:1;}}
        .nut-nhan{margin-top:25px;opacity:0;animation:hienNut 1s 1.8s forwards;}
        @keyframes hienNut{to{opacity:1;}}

        /* THẺ CẦU THỦ CÓ ẢNH RIÊNG */
        .the-ct{border-radius:14px;padding:0;text-align:center;border:3px solid;min-width:250px;overflow:hidden;background:#111;}
        .the-dong{border-color:var(--dong);}
        .the-bac{border-color:var(--bac);}
        .the-vang{border-color:var(--vang);}
        .the-cam{border-color:var(--cam);box-shadow:0 0 30px rgba(255,107,0,0.5);}
        .the-icon{border-color:var(--tim);box-shadow:0 0 30px rgba(147,51,234,0.5);}
        .anh-ct-the{width:100%;height:180px;object-fit:cover;background:#222;}
        .thong-tin-the{padding:12px;}
        .icon-loai-the{font-size:24px;margin-bottom:5px;}
        .ovr-lon{font-size:32px;font-weight:700;color:var(--vang);display:inline-block;margin:0 10px;}
        .ten-ct-lon{font-size:16px;font-weight:700;margin:8px 0;}

        /* GIAO DIỆN CHUNG */
        .san-nen{position:fixed;inset:0;background:url('https://images.unsplash.com/photo-1574629810360-7efbbe195018?fit=crop&w=1000&q=80') center/cover no-repeat;opacity:0.12;z-index:-1;}
        .menu{position:sticky;top:0;display:flex;background:rgba(0,0,0,0.85);border-radius:12px;padding:6px;margin-bottom:15px;backdrop-filter:blur(10px);z-index:99;}
        .menu-item{flex:1;text-align:center;padding:10px 4px;font-size:11px;font-weight:600;border-radius:8px;cursor:pointer;transition:0.2s;}
        .menu-item.active{background:var(--vang);color:#000;box-shadow:0 2px 10px rgba(255,193,7,0.5);}
        .khoang{background:rgba(255,255,255,0.07);border-radius:14px;padding:16px;margin-bottom:15px;border:1px solid rgba(255,255,255,0.1);}
        .tieu-de{color:var(--vang);font-size:18px;font-weight:700;text-align:center;margin-bottom:12px;}
        .tieu-de-nho{font-size:15px;color:var(--vang);margin:10px 0 6px 0;}
        .dong{display:flex;justify-content:space-between;align-items:center;padding:9px 0;font-size:14px;border-bottom:1px solid rgba(255,255,255,0.1);}
        .dong-cuoi{border:none;}
        .gia{color:var(--vang);font-weight:700;}
        .bar{width:100%;height:18px;background:rgba(0,0,0,0.5);border-radius:9px;overflow:hidden;margin:10px 0;}
        .bar-fill{height:100%;background:linear-gradient(90deg,var(--vang),#ffda6a);width:0%;transition:0.5s;}
        .btn{border:none;border-radius:10px;padding:10px 12px;font-weight:700;font-size:12px;cursor:pointer;transition:0.15s;}
        .btn-vang{background:var(--vang);color:#000;box-shadow:0 3px 0 #997404;}
        .btn-xanh{background:#198754;color:#fff;box-shadow:0 3px 0 #0f5132;}
        .btn-do{background:var(--do);color:#fff;box-shadow:0 3px 0 #a52a38;}
        .btn-tim{background:var(--tim);color:#fff;box-shadow:0 3px 0 #6b21a8;}
        .btn:disabled{opacity:0.4;box-shadow:none;transform:none;}
        .ten-goi{display:flex;align-items:center;gap:8px;}
        .icon-goi{font-size:20px;}
        .trang{display:none;}
        .trang.hien{display:block;}

        /* ĐỘI HÌNH 4-3-3 */
        .so-do-san{width:100%;aspect-ratio:2/3;background:linear-gradient(to bottom,#1a5c3a 0%,#207a4e 100%);border-radius:12px;border:3px solid rgba(255,255,255,0.3);position:relative;overflow:hidden;margin:10px 0;}
        .ke-doc,.ke-ngang{position:absolute;background:rgba(255,255,255,0.4);}
        .ke-doc{left:50%;top:0;bottom:0;width:2px;transform:translateX(-50%);}
        .ke-ngang{top:50%;left:0;right:0;height:2px;transform:translateY(-50%);}
        .vong-trung-tam{position:absolute;left:50%;top:50%;width:30%;aspect-ratio:1/2;border:2px solid rgba(255,255,255,0.4);border-radius:50%;transform:translate(-50%,-50%);}
        .vi-tri-ct{position:absolute;width:18%;aspect-ratio:1/1;transform:translate(-50%,-50%);cursor:pointer;transition:0.2s;}
        .vi-tri-ct:hover{transform:translate(-50%,-50%) scale(1.1);z-index:10;}
        .anh-tren-san{width:100%;height:100%;border-radius:50%;object-fit:cover;border:2px solid #fff;background:rgba(0,0,0,0.7);}
        .so-ovr-nho{position:absolute;bottom:2px;right:2px;background:rgba(0,0,0,0.7);color:var(--vang);font-weight:700;font-size:12px;padding:2px 4px;border-radius:4px;}
        .ten-nho{position:absolute;bottom:2px;left:2px;background:rgba(0,0,0,0.7);font-size:9px;padding:2px 3px;border-radius:4px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;max-width:70%;}
        .vt-tm{left:50%;top:12%;}.vt-hv1{left:22%;top:28%;}.vt-hv2{left:38%;top:28%;}.vt-hv3{left:62%;top:28%;}.vt-hv4{left:78%;top:28%;}
        .vt-tv1{left:30%;top:50%;}.vt-tv2{left:50%;top:45%;}.vt-tv3{left:70%;top:50%;}
        .vt-td1{left:35%;top:75%;}.vt-td2{left:65%;top:75%;}.vt-td3{left:90%;top:75%;}
        .trong{border:2px dashed rgba(255,255,255,0.5);background:rgba(0,0,0,0.3);display:flex;align-items:center;justify-content:center;font-size:24px;}

        /* POPUP CHI TIẾT */
        .popup{position:fixed;inset:0;background:rgba(0,0,0,0.85);z-index:995;display:none;align-items:center;justify-content:center;padding:15px;}
        .khung-popup{width:100%;max-width:360px;background:#111;border-radius:16px;padding:20px;border:2px solid var(--vang);text-align:center;}
        .anh-popup{width:100%;height:220px;object-fit:cover;border-radius:12px;margin-bottom:15px;}
        .tt-phu{display:grid;grid-template-columns:1fr 1fr;gap:8px 12px;margin:15px 0;text-align:left;}
        .dong-tt{display:flex;flex-direction:column;}
        .nho{font-size:11px;opacity:0.6;}
        .lon{font-size:14px;font-weight:600;}
        .chi-so{margin-top:15px;text-align:left;}
        .bar-cs{width:100%;height:10px;background:#333;border-radius:5px;overflow:hidden;margin:4px 0;}
        .do-cs{height:100%;background:linear-gradient(90deg,#ff4444,#ff8800,#44ff44);width:0%;transition:0.3s;}
    </style>
</head>
<body>

<!-- INTRO + THANH TẢI -->
<div id="introGame">
    <div class="logo-ea">EA SPORTS™</div>
    <div class="slogan">FIFA ONLINE 4 × CLB NINH BÌNH UNITED</div>
    <div class="khoang-tai">
        <div class="thong-tin-tai"><span id="trang-thai-tai">Đang tải tài nguyên...</span><span id="phan-tram-tai">0%</span></div>
        <div class="thanh-tai"><div class="do-tai" id="thanh-tai"></div></div>
        <div class="thong-tin-tai" style="margin-top:5px;"><span id="dung-luong-hien">0 MB</span><span>/ 18.6 MB</span></div>
    </div>
    <div class="man-chuyen"></div>
</div>

<div class="san-nen"></div>

<!-- MENU -->
<div class="menu">
    <div class="menu-item active" onclick="chuyen('tong')">Tổng quan</div>
    <div class="menu-item" onclick="chuyen('nhiemvu')">Nhiệm vụ</div>
    <div class="menu-item" onclick="chuyen('hop')">Mở thẻ</div>
    <div class="menu-item" onclick="chuyen('doi')">Đội hình</div>
    <div class="menu-item" onclick="chuyen('giao')">Giao hữu</div>
</div>

<!-- TRANG TỔNG QUAN -->
<div id="tong" class="trang hien">
    <div class="khoang">
        <div class="tieu-de">🏟️ CLB NINH BÌNH UNITED</div>
        <div class="dong"><span>Cấp HLV:</span><span id="cap-hlv">Cấp 1 - Tập Sự</span></div>
        <div class="dong"><span>Điểm XP:</span><span id="xp-hien">0</span> / <span id="xp-can">10.000</span></div>
        <div class="bar"><div class="bar-fill" id="bar-xp"></div></div>
        <div class="dong"><span>Tiền FC:</span><span class="gia" id="tien">200.000</span></div>
        <div class="dong"><span>Tổng OVR đội:</span><span id="tong-ovr">0</span></div>
    </div>
</div>

<!-- TRANG NHIỆM VỤ -->
<div id="nhiemvu" class="trang">
    <div class="khoang">
        <div class="tieu-de">📋 DANH SÁCH NHIỆM VỤ</div>
        <div class="tieu-de-nho">🔹 Hôm nay</div>
        <div class="nhom-nhiemvu">
            <div class="dong"><span>Tiếng Anh: Học 20 từ mới</span><button class="btn btn-do" onclick="lamNhiemVu('ta1')" id="btn-ta1">+1.200 XP</button></div>
            <div class="dong"><span>Toán: Giải 10 bài tập</span><button class="btn btn-xanh" onclick="lamNhiemVu('toan')" id="btn-toan">+1.600 XP</button></div>
            <div class="dong dong-cuoi"><span>Nghỉ ngơi sau khi học</span><button class="btn btn-xanh" onclick="lamNhiemVu('nghi')" id="btn-nghi">+500 XP</button></div>
        </div>
    </div>
</div>

<!-- TRANG MỞ THẺ -->
<div id="hop" class="trang">
    <div class="khoang">
        <div class="tieu-de">🎁 CỬA HÀNG GÓI THẺ</div>
        <div class="dong"><span>Số dư FC:</span><span class="gia" id="tien-hop">200.000</span></div>
    </div>
    <div class="khoang">
        <div class="dong"><div class="ten-goi"><span class="icon-goi">🥉</span>Gói Đồng</div><button class="btn" style="background:var(--dong);color:#000;" onclick="moThe('dong')">25.000</button></div>
        <div class="dong"><div class="ten-goi"><span class="icon-goi">🥈</span>Gói Bạc</div><button class="btn" style="background:var(--bac);color:#000;" onclick="moThe('bac')">70.000</button></div>
        <div class="dong"><div class="ten-goi"><span class="icon-goi">🥇</span>Gói Vàng</div><button class="btn" style="background:var(--vang);color:#000;" onclick="moThe('vang')">180.000</button></div>
        <div class="dong"><div class="ten-goi"><span class="icon-goi">🔥</span>Gói Huyền Thoại</div><button class="btn" style="background:var(--cam);color:#fff;" onclick="moThe('cam')">400.000</button></div>
        <div class="dong dong-cuoi"><div class="ten-goi"><span class="icon-goi">💎</span>Gói Icon</div><button class="btn btn-tim" onclick="moThe('icon')">900.000</button></div>
    </div>
</div>

<!-- TRANG ĐỘI HÌNH -->
<div id="doi" class="trang">
    <div class="khoang">
        <div class="tieu-de">👕 SƠ ĐỒ ĐỘI HÌNH 4-3-3</div>
        <div class="so-do-san" id="so-do">
            <div class="ke-doc"></div><div class="ke-ngang"></div><div class="vong-trung-tam"></div>
            <div class="vi-tri-ct vt-tm" onclick="xemChiTiet(0)"></div>
            <div class="vi-tri-ct vt-hv1" onclick="xemChiTiet(1)"></div>
            <div class="vi-tri-ct vt-hv2" onclick="xemChiTiet(2)"></div>
            <div class="vi-tri-ct vt-hv3" onclick="xemChiTiet(3)"></div>
            <div class="vi-tri-ct vt-hv4" onclick="xemChiTiet(4)"></div>
            <div class="vi-tri-ct vt-tv1" onclick="xemChiTiet(5)"></div>
            <div class="vi-tri-ct vt-tv2" onclick="xemChiTiet(6)"></div>
            <div class="vi-tri-ct vt-tv3" onclick="xemChiTiet(7)"></div>
            <div class="vi-tri-ct vt-td1" onclick="xemChiTiet(8)"></div>
            <div class="vi-tri-ct vt-td2" onclick="xemChiTiet(9)"></div>
            <div class="vi-tri-ct vt-td3" onclick="xemChiTiet(10)"></div>
        </div>
    </div>
</div>

<!-- TRANG GIAO HỮU -->
<div id="giao" class="trang">
    <div class="khoang">
        <div class="tieu-de">⚔️ ĐẤU GIAO HỮU</div>
        <div class="dong"><span>CLB Hà Nội - OVR 76</span><button class="btn btn-vang" onclick="daDau(76)">Đấu</button></div>
        <div id="kq" style="margin-top:15px;text-align:center;font-weight:700;"></div>
    </div>
</div>

<!-- MỞ THẺ -->
<div id="manMoThe">
    <div class="hop-mo">📦</div><div class="tia-sang"></div>
    <div class="kq-the" id="kqThe"></div>
    <div class="ten-dac-biet" id="tenDacBiet"></div>
    <div class="nut-nhan"><button class="btn btn-vang" style="width:220px;" onclick="dongMoThe()">NHẬN CẦU THỦ</button></div>
</div>

<!-- POPUP CHI TIẾT -->
<div class="popup" id="popupCt">
    <div class="khung-popup">
        <img src="" alt="Ảnh cầu thủ" class="anh-popup" id="anhPopup">
        <div class="tieu-de" id="tenCt">-</div>
        <div class="tt-phu">
            <div class="dong-tt"><span class="nho">Vị trí</span><span class="lon" id="vtCt">-</span></div>
            <div class="dong-tt"><span class="nho">Chiều cao</span><span class="lon" id="caoCt">-</span></div>
            <div class="dong-tt"><span class="nho">Quốc tịch</span><span class="lon" id="qtCt">-</span></div>
            <div class="dong-tt"><span class="nho">Tổng OVR</span><span class="lon" id="ovrCt">-</span></div>
        </div>
        <div class="chi-so">
            <div class="dong" style="border:none;padding:2px 0;"><span>Tốc độ</span><span id="cs-tocdo">0</span></div>
            <div class="bar-cs"><div class="do-cs" id="bar-tocdo"></div></div>
            <div class="dong" style="border:none;padding:2px 0;"><span>Tấn công</span><span id="cs-tancong">0</span></div>
            <div class="bar-cs"><div class="do-cs" id="bar-tancong"></div></div>
        </div>
        <button class="btn btn-vang" style="width:100%;margin-top:15px;" onclick="dongPopup()">Đóng</button>
    </div>
</div>

<script>
// 50 LINK ẢNH KHÁC NHAU HOÀN TOÀN
const DANH_SACH_ANH = [
"https://images.unsplash.com/photo-1579952363873-27f3bade9f55?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1552058544-f2b08422138a?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1543326727-cf6c39e81324?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1517466787929-bc90951d0974?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1508098682722-e99c43a406b2?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1560272564-c83b66b1ad12?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1568602471122-7832951cc4c5?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1542744173-8e7e53415bb0?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1521412644187-c49fa049e84d?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1574629810360-7efbbe195018?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1593030103066-0093718efeb9?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1551958219-acbc608c6377?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1546519638-68e109498ffc?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1532748298210-8c0c5d098e2d?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1519861531473-9200262188bf?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1505666280221-31f021478c95?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1493711662062-fa541f7f3d24?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-148994444061a-453fc2b6a9a9?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1471295294237-1c4e6b67498e?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1580089595283-b54e43b578d0?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1578926375605-eaf7559b1458?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1574629135783-8e21a7891993?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1565992441121-82d9885f0f06?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1559827291-72ee739d0d9a?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1556895953-f8f191115982?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1549576490-b0b4831ef60a?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1542204165-6bfdb6e08507?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1514222134-b57cbb8ce073?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1503398392009-93248d16c16b?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1501281668745-f7f57925c3b4?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1463613607015-4b9da0e13b6c?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1587280501635-68a0e82cd5ff?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1582552938357-32b906df40cb?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1581966799305-979d23308c5e?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1576599799215-1b7b9cfb456c?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1571167366157-0ba4d6fca5a6?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1565051522697-430c72d0f14d?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1547153760-18fc8642bfc1?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1533230315837-80e703b68b02?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1524592168983-5d1675c0e319?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1516466723877-e4ec1d736c8a?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1511671782779-c97d3d27a1d4?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1495566021144-451f15e70a8d?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1488590528505-98d2b5aba04b?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1476480862126-209bfaa8edc8?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1431324155629-1a6deb1dec8d?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1419242902214-279d525c7214?w=300&h=400&fit=crop",
"https://images.unsplash.com/photo-1596796687951-88e01b58f261?w=300&h=400&fit=crop"
];
let chiSoAnhDaDung = [];

// CHẠY THANH TẢI
function chayThanhTai(){
    const tongMB = 18.6;
    let phanTram = 0;
    const interval = setInterval(()=>{
        phanTram += Math.floor(Math.random()*4)+1;
        if(phanTram>=100){phanTram=100;clearInterval(interval);}
        document.getElementById('thanh-tai').style.width = phanTram+'%';
        document.getElementById('phan-tram-tai').textContent = phanTram+'%';
        document.getElementById('dung-luong-hien').textContent = (tongMB*phanTram/100).toFixed(1)+' MB';
    },120);
}

// BẢNG XP & DỮ LIỆU
const bangXPCap = [
    {cap:1,xp:10000,ten:"Tập Sự"},{cap:2,xp:25000,ten:"Mới Bắt Đầu"},{cap:3,xp:50000,ten:"HLV Phó"},
    {cap:4,xp:100000,ten:"HLV Chính Thức"},{cap:5,xp:200000,ten:"HLV Xuất Sắc"},{cap:6,xp:350000,ten:"HLV Chuyên Nghiệp"},
    {cap:7,xp:500000,ten:"HLV Đỉnh Cao"},{cap:8,xp:750000,ten:"HLV Huyền Thoại"},{cap:9,xp:1000000,ten:"HLV Vĩ Đại Nhất"}
];
let clb = JSON.parse(localStorage.getItem('luuFO4_NinhBinh')) || {
    xp:0,tien:200000,capHien:1,daLam:{ta1:false,toan:false,van:false,nghi:false},cauThu:[]
};
const ho = ["Nguyễn","Trần","Lê","Phạm","Messi","Ronaldo","Mbappé","Haaland"];
const ten = ["Quang Hải","Tiến Linh","Công Phượng","Văn Lâm","Modrić","De Bruyne","Kane","Vinicius"];
const viTri = ["Thủ môn","Hậu vệ trái","Trung vệ","Trung vệ","Hậu vệ phải","TV phòng ngự","TV trung tâm","TV tấn công","Tiền đạo trái","Tiền đạo trung tâm","Tiền đạo phải"];
const quocTich = ["Việt Nam","Argentina","Bồ Đào Nha","Pháp","Brazil","Đức"];
const clbList = ["Ninh Bình FC","Hà Nội FC","Real Madrid","Man City","Bayern Munich"];
const iconThe = {dong:'🥉',bac:'🥈',vang:'🥇',cam:'🔥',icon:'💎'};
const tenLoaiThe = {dong:'Thẻ Đồng',bac:'Thẻ Bạc',vang:'Thẻ Vàng',cam:'Huyền Thoại',icon:'Icon'};
const giaGoi = {dong:25000,bac:70000,vang:180000,cam:400000,icon:900000};
const ovrGoi = {dong:[58,67],bac:[68,79],vang:[80,89],cam:[90,94],icon:[94,97]};

// LƯU & CẬP NHẬT
function luu(){localStorage.setItem('luuFO4_NinhBinh',JSON.stringify(clb));capNhatGiaoDien();capNhatSoDo();}
function capNhatGiaoDien(){
    let cap=1,xpTiepTheo=bangXPCap[0].xp;
    for(let i=0;i<bangXPCap.length;i++){if(clb.xp>=bangXPCap[i].xp){cap=bangXPCap[i].cap;xpTiepTheo=i<bangXPCap.length-1?bangXPCap[i+1].xp:bangXPCap[i].xp;}}
    document.getElementById('cap-hlv').textContent=`Cấp ${cap} - ${bangXPCap[cap-1].ten}`;
    document.getElementById('xp-hien').textContent=clb.xp.toLocaleString();
    document.getElementById('xp-can').textContent=xpTiepTheo.toLocaleString();
    document.getElementById('bar-xp').style.width=Math.min((clb.xp/xpTiepTheo)*100,100)+'%';
    document.getElementById('tien').textContent=clb.tien.toLocaleString();
    document.getElementById('tien-hop').textContent=clb.tien.toLocaleString();
    const tongOvr = clb.cauThu.length?Math.round(clb.cauThu.reduce((a,b)=>a+b.ovr,0)/clb.cauThu.length):0;
    document.getElementById('tong-ovr').textContent = tongOvr;
}

// CẬP NHẬT ĐỘI HÌNH CÓ ẢNH RIÊNG
function capNhatSoDo(){
    const viTriDom = document.querySelectorAll('.vi-tri-ct');
    viTriDom.forEach((o,i)=>{
        o.innerHTML='';o.classList.remove('trong');
        if(clb.cauThu[i]){
            const ct = clb.cauThu[i];
            o.innerHTML = `<img src="${ct.anh}" alt="${ct.ten}" class="anh-tren-san"><div class="so-ovr-nho">${ct.ovr}</div><div class="ten-nho">${ct.ten.split(' ').slice(-2).join(' ')}</div>`;
        }else o.classList.add('trong');
    });
}

// CHUYỂN TRANG
function chuyen(trang){
    document.querySelectorAll('.trang').forEach(i=>i.classList.remove('hien'));
    document.querySelectorAll('.menu-item').forEach(i=>i.classList.remove('active'));
    document.getElementById(trang).classList.add('hien');
    event.target.classList.add('active');
}

// HOÀN THÀNH NHIỆM VỤ
function lamNhiemVu(ma){
    if(clb.daLam[ma]) return;
    const thuong = {ta1:{xp:1200},toan:{xp:1600},van:{xp:1300},nghi:{xp:500}};
    clb.daLam[ma]=true;clb.xp+=thuong[ma].xp;luu();
    alert(`✅ Hoàn thành! +${thuong[ma].xp.toLocaleString()} XP`);
}

// LẤY ẢNH CHƯA DÙNG - KHÔNG TRÙNG
function layAnhNgauNhien(){
    if(chiSoAnhDaDung.length >= DANH_SACH_ANH.length){
        chiSoAnhDaDung = [];
    }
    let chiSo;
    do{chiSo = Math.floor(Math.random()*DANH_SACH_ANH.length);}
    while(chiSoAnhDaDung.includes(chiSo));
    chiSoAnhDaDung.push(chiSo);
    return DANH_SACH_ANH[chiSo];
}

// MỞ THẺ CÓ ẢNH RIÊNG
function moThe(loai){
    if(clb.cauThu.length>=11) return alert('Đủ 11 cầu thủ!');
    if(clb.tien<giaGoi[loai]) return alert('Không đủ FC!');
    clb.tien -= giaGoi[loai]; luu();
    const man = document.getElementById('manMoThe');
    const kqThe = document.getElementById('kqThe');
    man.style.display='flex';kqThe.classList.remove('hien-the-xong');
    setTimeout(()=>{
        const ct = taoCauThu(loai);clb.cauThu.push(ct);luu();
        kqThe.innerHTML = `<div class="the-ct the-${loai}">
            <img src="${ct.anh}" alt="${ct.ten}" class="anh-ct-the">
            <div class="thong-tin-the">
                <div class="icon-loai-the">${iconThe[loai]}</div>
                <span class="ovr-lon">${ct.ovr}</span>
                <div class="ten-ct-lon">${ct.ten}</div>
                <div style="font-size:13px;opacity:0.8;">${tenLoaiThe[loai]}</div>
            </div>
        </div>`;
        kqThe.classList.add('hien-the-xong');
    },2000);
}
function dongMoThe(){document.getElementById('manMoThe').style.display='none';}

// TẠO CẦU THỦ CÓ ẢNH RIÊNG
function taoCauThu(loai){
    const khoang = ovrGoi[loai];
    const ovr = Math.floor(Math.random()*(khoang[1]-khoang[0]+1)) + khoang[0];
    return {
        ten: ho[Math.floor(Math.random()*ho.length)] + ' ' + ten[Math.floor(Math.random()*ten.length)],
        ovr: ovr,
        cao: (165 + Math.floor(Math.random()*22)) + ' cm',
        quocTich: quocTich[Math.floor(Math.random()*quocTich.length)],
        clb: clbList[Math.floor(Math.random()*clbList.length)],
        loai: loai,
        anh: layAnhNgauNhien(),
        tocdo: Math.floor(ovr - 5 + Math.random()*12),
        tancong: Math.floor(ovr - 3 + Math.random()*10)
    };
}

// XEM CHI TIẾT CÓ ẢNH
function xemChiTiet(i){
    if(!clb.cauThu[i]) return alert('Chưa có cầu thủ!');
    const ct = clb.cauThu[i];
    document.getElementById('anhPopup').src = ct.anh;
    document.getElementById('tenCt').textContent = ct.ten;
    document.getElementById('vtCt').textContent = viTri[i];
    document.getElementById('caoCt').textContent = ct.cao;
    document.getElementById('qtCt').textContent = ct.quocTich;
    document.getElementById('ovrCt').textContent = ct.ovr;
    ['tocdo','tancong'].forEach(s=>{document.getElementById('cs-'+s).textContent=ct[s];document.getElementById('bar-'+s).style.width=ct[s]+'%';});
    document.getElementById('popupCt').style.display='flex';
}
function dongPopup(){document.getElementById('popupCt').style.display='none';}

// GIAO HỮU
function daDau(doiOvr){
    const toi = clb.cauThu.length?Math.round(clb.cauThu.reduce((a,b)=>a+b.ovr,0)/clb.cauThu.length):62;
    const kq = document.getElementById('kq');
    if(toi>doiOvr+5){kq.textContent='🏆 THẮNG! +25.000 FC';kq.style.color='#44ff44';clb.tien+=25000;
