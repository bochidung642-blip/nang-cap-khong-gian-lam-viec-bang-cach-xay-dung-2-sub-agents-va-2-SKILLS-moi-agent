# Meta Ads (Facebook & Instagram Ads)

## Cấu Trúc Campaign

```
Campaign (Mục tiêu)
└── Ad Set (Đối tượng + Ngân sách + Lịch chạy)
    └── Ad (Creative: ảnh/video/copy)
```

### Campaign Objectives và khi nào dùng

| Objective | Khi nào dùng |
|-----------|-------------|
| Awareness | Brand mới, reach rộng |
| Traffic | Drive traffic về website/landing page |
| Engagement | Tăng tương tác, comment, like |
| Leads | Thu thập thông tin qua Lead Form hoặc website |
| App Promotion | Tăng install / in-app actions |
| Sales / Conversions | Tối ưu purchase, add-to-cart (cần Pixel) |

---

## Audience Targeting

### 3 Layer Audience

**1. Cold Audience (Top of Funnel)**
- Interest targeting: sở thích, hành vi, demographics
- Lookalike Audience (LAL): 1-3% giống khách hàng hiện tại
- Broad targeting: để Meta tự tối ưu (Advantage+ Audience)

**2. Warm Audience (Middle of Funnel)**
- Website visitors (cần Pixel): 7/14/30/60 ngày
- Video viewers: xem 50%/75%/95% video
- Instagram/Facebook page engagers
- Lead form openers (chưa submit)

**3. Hot Audience (Bottom of Funnel)**
- Purchase lookalike
- Add to cart nhưng chưa mua
- Past customers (retarget upsell/cross-sell)
- Email list custom audience

### Audience Size Guidelines
| Loại | Size tối thiểu | Gợi ý |
|------|---------------|-------|
| Cold - Interest | 500K - 5M | Tránh quá rộng hoặc quá hẹp |
| Cold - Broad | 2M+ | Phù hợp khi budget lớn |
| Lookalike | 1-3% (VN ~600K-1.8M) | 1% converters tốt nhất |
| Retargeting | 1,000+ | Cần đủ lượng cho delivery |

---

## Budget & Bidding

### Daily Budget vs Lifetime Budget
- **Daily**: Linh hoạt, dễ scale, tránh over-delivery
- **Lifetime**: Kiểm soát tổng ngân sách, phù hợp campaign có deadline

### CBO vs ABO
- **CBO (Campaign Budget Optimization)**: Meta tự phân bổ budget giữa các ad sets — phù hợp khi đã biết audience nào win
- **ABO (Ad Set Budget Optimization)**: Kiểm soát budget từng ad set — phù hợp khi testing audiences mới

### Bidding Strategies
| Strategy | Khi nào dùng |
|----------|-------------|
| Lowest Cost (auto) | Mặc định, tốt cho hầu hết trường hợp |
| Cost Cap | Kiểm soát CPA, scale trong giới hạn chi phí |
| Bid Cap | Kiểm soát bid tuyệt đối, risk giảm delivery |
| ROAS Goal | Khi có đủ data conversion (50+ conversions/tuần) |

### Quy tắc tăng budget an toàn
- Tăng tối đa **20% mỗi 3-4 ngày** để tránh reset learning phase
- Nếu cần tăng nhanh: duplicate ad set với budget mới thay vì chỉnh trực tiếp

---

## Creative Best Practices

### Video Ads
- Hook trong 3 giây đầu (text overlay + action mạnh)
- Tỷ lệ 4:5 hoặc 9:16 cho feed/Reels
- Phụ đề bắt buộc (85% xem không có âm thanh)
- Độ dài lý tưởng: 15-30 giây cho conversion, 60+ cho awareness

### Image Ads
- Tỷ lệ 1:1 hoặc 4:5
- High contrast, bắt mắt khi scroll
- Ít text trên ảnh (Meta khuyến nghị)
- Headline rõ ràng, benefit-focused

### Ad Copy Structure
```
Primary Text: Hook + Value proposition + CTA (125 ký tự đầu quan trọng)
Headline: Lợi ích chính (dưới 40 ký tự)
Description: Hỗ trợ thêm thông tin
CTA Button: Chọn đúng với mục tiêu (Learn More / Shop Now / Get Quote)
```

### Dynamic Creative
- Cung cấp nhiều assets (5 images, 5 videos, 5 headlines, 5 descriptions)
- Meta tự kết hợp và tối ưu
- Phù hợp khi testing ở giai đoạn đầu

---

## Learning Phase & Campaign Management

### Learning Phase
- Campaign cần **50 optimization events trong 7 ngày** để thoát Learning Phase
- Tránh thay đổi trong Learning Phase (thay đổi lớn → reset)
- Các thay đổi KHÔNG reset Learning: Chỉnh budget nhỏ (dưới 20%), bật/tắt ads cùng ad set

### Khi nào kill ad / ad set
- CPC quá cao (gấp 2-3x benchmark) sau 3-5 ngày
- CTR dưới 1% (thường là do creative kém)
- Frequency > 4-5 lần (audience saturation)
- CPL/CPA vượt 2x target sau 50+ impressions

### A/B Testing Framework
- Chỉ test **1 biến số** mỗi lần (audience / creative / placement / objective)
- Budget đủ lớn: mỗi variant cần ít nhất 100-200 reach/ngày
- Chạy ít nhất **7 ngày** trước khi kết luận
- Statistical significance: 95%+ để tin cậy kết quả
