# Dữ liệu văn hóa cho Blogspot/GitHub

## File chính
- `van_hoa_data.js`: dùng trực tiếp bằng thẻ `<script>` trong Blogspot.
- `van_hoa_data.json`: bản JSON thuần, dùng nếu app của bạn fetch JSON.

## Cấu trúc dữ liệu
- `window.VAN_HOA_DATA.categories`: danh sách mục, giữ đúng theo các file DOCX trong ZIP.
- `window.VAN_HOA_DATA.posts`: danh sách bài viết. Mỗi `Heading 1` trong DOCX được tách thành một bài riêng.
- Mỗi bài có: `id`, `slug`, `title`, `categoryName`, `categorySlug`, `excerpt`, `blocks`, `html`, `wordCount`, `sectionCount`.

## Nhúng trong Blogspot
```html
<script src="https://cdn.jsdelivr.net/gh/TEN_USER/TEN_REPO/van_hoa_data.js"></script>
<script>
  const data = window.VAN_HOA_DATA;
  const categories = data.categories;
  const posts = data.posts;

  // Ví dụ: lấy bài theo mục Truyện cổ
  const truyenCo = posts.filter(p => p.categorySlug === 'truyen-co');

  // Render nhanh bài đầu tiên
  document.getElementById('app').innerHTML = `
    <h1>${posts[0].title}</h1>
    <article>${posts[0].html}</article>
  `;
</script>
```

## Thống kê
- Số mục: 6
- Số bài: 233
- Tổng số từ ước tính: 536308
