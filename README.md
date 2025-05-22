body {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    margin: 0;
    background-color: #f0f0f0; /* Nền nhẹ bên ngoài khung chính */
    font-family: sans-serif;
    position: relative;
    overflow: hidden; /* Ngăn chặn scrollbar nếu annotation ra ngoài */
}

.viewport-container {
    /* Kích thước được tính toán dựa trên hình ảnh mục tiêu và lề 20px */
    width: 1342px; /* 20(lề trái) + 992(khối xanh lá) + 10(gap) + 300(khối teal) + 20(lề phải) */
    height: 1190px; /* 20(lề trên) + tổng chiều cao cột trái + 20(lề dưới) */
    border: 2px solid #cccc00; /* Khung vàng */
    background-color: #e0e0e0; /* Nền xám nhạt bên trong khung */
    position: relative; /* Cho phép định vị tuyệt đối các phần tử con */
    box-sizing: border-box; /* Đảm bảo padding/border không làm tăng kích thước tổng thể */
}

/* Base style cho tất cả các khối màu */
.box {
    position: absolute; /* Tất cả các khối sẽ được định vị tuyệt đối */
    box-sizing: border-box; /* Đảm bảo padding/border không làm tăng kích thước */
    border: 1px solid rgba(128, 128, 128, 0.2); /* Đường viền xám nhạt, độ mờ 20% */
}

/* Các khối màu cụ thể với kích thước và vị trí chính xác theo hình ảnh */

.light-green {
    background-color: #90EE90; /* Xanh lá nhạt */
    width: 992px;
    height: 90px;
    top: 20px;
    left: 20px;
}

.light-blue {
    background-color: #ADD8E6; /* Xanh dương nhạt */
    width: 320px;
    height: 300px;
    top: calc(20px + 90px + 10px);
    left: 20px;
}

.yellow-top {
    background-color: #FFFF00; /* Vàng */
    width: 372px;
    height: 300px;
    top: calc(20px + 90px + 10px);
    left: calc(20px + 320px + 10px);
}

.purple {
    background-color: #800080; /* Tím */
    width: 692px;
    height: 300px;
    top: calc(20px + 90px + 10px + 300px + 10px);
    left: 20px;
}

.pink {
    background-color: #FFC0CB; /* Hồng */
    width: 692px;
    height: 300px;
    top: calc(20px + 90px + 10px + 300px + 10px + 300px + 10px);
    left: 20px;
}

.yellow-bottom-main {
    background-color: #FFFF00; /* Vàng */
    width: 692px;
    height: 90px;
    top: calc(20px + 90px + 10px + 300px + 10px + 300px + 10px + 300px + 10px);
    left: 20px;
}

/* KHỐI XANH MÒNG KÉT (TEAL) ĐÃ ĐƯỢC CHUYỂN VỊ TRÍ */
.teal {
    background-color: #008080; /* Xanh mòng két */
    width: 300px;
    height: 990px;
    top: calc(20px + 90px + 10px); /* Căn thẳng hàng với đỉnh của khối light-blue và yellow-top */
    left: calc(20px + 320px + 10px + 372px + 10px); /* Nằm bên phải khối vàng phía trên, cách 10px */
}

/* STYLE CHUNG CHO CÁC DÒNG CHỮ */
.text {
    position: absolute;
    font-size: 14px;
    color: #333;
    white-space: nowrap;
    z-index: 10;
}

/* Vị trí các dòng chữ cụ thể */
.header-text {
    top: 10px;
    left: 10px;
}

.footer-text {
    bottom: 10px;
    left: calc(20px + 692px / 2); /* Căn giữa trên khối vàng dưới cùng */
    transform: translateX(-50%);
    padding: 2px 8px;
    background-color: rgba(255, 255, 255, 0.7);
    border-radius: 3px;
}

/* Annotations bên ngoài khung chính */
.annotation {
    font-size: 14px;
    color: #333;
}

.annotation-left {
    left: -40px;
    top: 50%;
    transform: translateY(-50%) rotate(-90deg);
}

.annotation-right {
    right: -40px;
    top: 50%;
    transform: translateY(-50%) rotate(90deg);
}

/* Mũi tên cho annotations */
.annotation-left::before {
    content: '';
    position: absolute;
    width: 0;
    height: 0;
    border-top: 8px solid transparent;
    border-bottom: 8px solid transparent;
    border-right: 8px solid #333;
    left: -10px;
    top: 50%;
    transform: translateY(-50%);
}

.annotation-right::before {
    content: '';
    position: absolute;
    width: 0;
    height: 0;
    border-top: 8px solid transparent;
    border-bottom: 8px solid transparent;
    border-left: 8px solid #333;
    right: -10px;
    top: 50%;
    transform: translateY(-50%);
}
