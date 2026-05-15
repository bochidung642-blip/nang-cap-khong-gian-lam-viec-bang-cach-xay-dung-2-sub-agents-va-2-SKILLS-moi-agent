# Tracking Setup cho Facebook Ads — Pixel, GTM, UTM, CAPI

## Meta Pixel

### Cài đặt Meta Pixel

**Cách 1: Manual (thêm vào `<head>`)**
```html
<!-- Meta Pixel Code -->
<script>
!function(f,b,e,v,n,t,s)
{if(f.fbq)return;n=f.fbq=function(){n.callMethod?
n.callMethod.apply(n,arguments):n.queue.push(arguments)};
if(!f._fbq)f._fbq=n;n.push=n;n.loaded=!0;n.version='2.0';
n.queue=[];t=b.createElement(e);t.async=!0;
t.src=v;s=b.getElementsByTagName(e)[0];
s.parentNode.insertBefore(t,s)}(window, document,'script',
'https://connect.facebook.net/en_US/fbevents.js');
fbq('init', 'YOUR_PIXEL_ID');
fbq('track', 'PageView');
</script>
```

**Cách 2: Qua Google Tag Manager (khuyến nghị)**
- Dùng template "Facebook Pixel" trong GTM Community Gallery
- Trigger: All Pages

**Cách 3: Plugin CMS**
- WordPress: Pixel Your Site, PixelCat
- Shopify: Meta channel chính thức

### Standard Events quan trọng

| Event | Khi nào fire | Code mẫu |
|-------|-------------|---------|
| PageView | Mọi trang | Tự động với pixel base |
| ViewContent | Trang sản phẩm | `fbq('track', 'ViewContent', {content_ids: ['SKU123'], content_type: 'product', value: 299000, currency: 'VND'})` |
| AddToCart | Thêm vào giỏ | `fbq('track', 'AddToCart', {value: 199000, currency: 'VND'})` |
| InitiateCheckout | Bắt đầu checkout | `fbq('track', 'InitiateCheckout')` |
| Purchase | Mua thành công | `fbq('track', 'Purchase', {value: 299000, currency: 'VND'})` |
| Lead | Submit form | `fbq('track', 'Lead')` |
| CompleteRegistration | Đăng ký thành công | `fbq('track', 'CompleteRegistration')` |

### Custom Events
Khi Standard Events không đủ:
```javascript
fbq('trackCustom', 'ClickedWhatsapp');
fbq('trackCustom', 'WatchedVideo50Percent');
```

---

## Conversions API (CAPI)

### Tại sao cần CAPI
- iOS 14+ và ad blockers làm Pixel bị miss events
- CAPI gửi data từ server → Meta server (không qua browser)
- Kết hợp Pixel + CAPI: redundancy, tăng match rate

### Match Rate tốt cần gửi
- `em` (email hash) — quan trọng nhất
- `ph` (phone hash)
- `fbp` (Facebook Browser ID từ cookie)
- `fbc` (Facebook Click ID từ URL)
- `external_id` (customer ID từ hệ thống của bạn)

### Cài CAPI qua GTM Server-side
1. Setup GTM Server Container
2. Cài Meta Pixel Tag (server-side)
3. Configure client và forwarding

### Cài CAPI qua nền tảng
- **Shopify**: Bật trong Meta channel settings
- **WordPress WooCommerce**: Plugin PixelYourSite Pro
- **Custom**: Dùng Meta Business SDK (Node.js / Python / PHP)

---

## Google Tag Manager (GTM) — Dùng cho Meta Pixel

### Setup GTM cơ bản

**Bước 1**: Cài Container code vào `<head>` và `<body>` của website.

**Bước 2**: Tạo Tag Meta Pixel
- Tag Type: Custom HTML (paste pixel code)
- Hoặc dùng template "Facebook Pixel" từ Gallery
- Trigger: All Pages

**Bước 3**: Tạo Trigger cho Conversion Events

**Trigger: Thank You Page (Purchase/Lead)**
```
Trigger Type: Page View
This trigger fires on: Page URL contains /thank-you
```

**Trigger: Form Submit**
```
Trigger Type: Form Submission
Wait for Tags: Enabled
Check Validation: Enabled
```

**Trigger: Button Click**
```
Trigger Type: All Elements
Fire when: Click Text contains "Đặt hàng"
```

---

## UTM Parameters

### Cú pháp UTM cho Facebook Ads
```
https://website.com/landing-page
?utm_source=facebook
&utm_medium=cpc
&utm_campaign=[tên_campaign]
&utm_content=[tên_adset_hoặc_creative]
&utm_term=[tên_ad]
```

### Naming Convention chuẩn
| Parameter | Giá trị mẫu | Ghi chú |
|-----------|------------|---------|
| utm_source | facebook | Luôn là "facebook" |
| utm_medium | cpc | Paid social |
| utm_campaign | brand-awareness-q2-2025 | Tên campaign, lowercase, dấu gạch ngang |
| utm_content | video-hook-v1, carousel-benefit | Phân biệt A/B creatives |
| utm_term | cold-interest-beauty | Ad set name |

**Quy tắc**: lowercase, dùng dấu gạch ngang thay khoảng trắng, nhất quán.

### Dynamic UTM trong Facebook Ads
Facebook hỗ trợ dynamic parameters:
```
utm_campaign={{campaign.name}}
utm_content={{adset.name}}
utm_term={{ad.name}}
```

---

## Kiểm Tra Tracking

### Meta Pixel Helper (Chrome Extension)
- Verify pixel đang fire đúng
- Xem events đang được gửi
- Debug duplicate events

### Facebook Events Manager
- Realtime event activity
- Match quality score
- Test events tool (test trực tiếp từ Events Manager)

### GTM Preview Mode
- Test tags trước khi publish
- Xem triggers nào được kích hoạt
- Debug variables

### Checklist trước khi chạy ads
- [ ] Pixel base code trên tất cả trang
- [ ] PageView event fire đúng
- [ ] Conversion events fire đúng trang/hành động (Purchase, Lead...)
- [ ] Test event thành công trên Facebook Events Manager
- [ ] UTM parameters setup cho tất cả ad links
- [ ] Không có duplicate events
- [ ] Match quality "Good" hoặc "Excellent" trên Events Manager
