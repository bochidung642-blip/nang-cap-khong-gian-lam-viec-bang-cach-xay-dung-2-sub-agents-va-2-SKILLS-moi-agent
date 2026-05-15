# Campaign Optimization — Facebook Ads

## Framework Tối Ưu Tổng Thể

```
Thu thập Data → Diagnose → Hypothesis → Test → Implement → Scale
```

---

## Metrics và Ngưỡng Benchmark (VN Market)

| Metric | Tốt | Trung bình | Cần xem xét |
|--------|-----|-----------|-------------|
| CTR (Link) | > 2% | 1-2% | < 1% |
| CPM | < 30K VND | 30K-70K | > 70K |
| CPC (Link) | < 3K VND | 3K-8K | > 8K |
| CPL (Lead) | Tùy ngành | — | > 3x target |
| ROAS | > 3x | 2-3x | < 2x |
| Frequency | < 3 | 3-5 | > 5 (saturation) |
| Quality Ranking | Above Average | Average | Below Average |
| Relevance Score | 7-10 | 5-6 | < 5 |

---

## Diagnose Framework

### CTR Thấp (< 1%)

```
CTR thấp
├── Creative issue → Hook không đủ mạnh, visual không bắt mắt
│     → Test hook mới, đổi format (video/image/carousel)
├── Audience mismatch → Content không relevant với audience
│     → Refine targeting, thử audience khác
├── Offer không hấp dẫn → Value proposition yếu
│     → Cải thiện headline và primary text
└── Placement không phù hợp → Tách placement riêng để so sánh
```

### CPL / CPA Cao

```
CPL cao
├── Traffic xấu → Audience quá rộng, exclude irrelevant
├── Landing page kém → CRO, tăng conversion rate trên LP
├── Offer không đủ mạnh → Cải thiện offer / lead magnet
├── Tracking lỗi → Verify pixel, conversion events
└── Campaign chưa thoát Learning Phase → Chờ 7 ngày / consolidate
```

### Delivery Kém (Spend thấp hơn budget)

```
Delivery thấp
├── Audience quá hẹp → Mở rộng targeting
├── Bid quá thấp → Tăng bid hoặc chuyển sang Lowest Cost
├── Creative bị reject → Kiểm tra Ad Quality trong Ads Manager
├── Budget quá thấp so với CPM → Tăng budget tối thiểu 5-10x CPM/ngày
└── Đang trong Learning Phase với ít conversions → Hợp nhất ad sets
```

### Frequency Cao (> 5)

```
Frequency cao → Audience saturation
├── Mở rộng audience (tăng size hoặc thêm interests mới)
├── Làm mới creative (creative fatigue)
├── Tạm dừng và để audience "rest" 1-2 tuần
└── Chuyển sang Lookalike mới từ recent customers
```

---

## Scaling Strategy

### Vertical Scaling (tăng budget)
- Tăng tối đa **20% mỗi 3-4 ngày**
- Chỉ scale winning ad sets (CPL < target, đã thoát Learning Phase)
- Theo dõi sát 48 giờ sau khi tăng budget

### Horizontal Scaling (nhân rộng)
- Duplicate ad set sang audiences mới (LAL%, interest khác, broad)
- Giữ nguyên winning creative khi test audience mới
- Test thêm placements (Facebook Feed vs Instagram Feed vs Reels)

### Creative Scaling
- Tìm winning creative → tạo 3-5 biến thể (khác hook, khác format, khác CTA)
- Không chỉnh sửa creative đang win — thêm creative mới vào ad set
- Khi creative cũ fatigue: test biến thể, không kill ngay

---

## A/B Testing Framework

### Priority test theo impact

1. **Offer / Value proposition** — impact lớn nhất
2. **Hook / Headline** — ảnh hưởng CTR
3. **Format** — video vs image vs carousel
4. **Audience** — cold vs warm, LAL vs interest
5. **Placement** — tách manual để so sánh
6. **CTA button** — Learn More vs Shop Now vs Get Quote
7. **Landing page** — different versions

### Thiết kế test đúng cách

```
Test 1 biến duy nhất mỗi lần

Ví dụ — Test Creative Hook:
- Control: Video với hook "Bạn có đang mắc lỗi này khi chạy ads?"
- Variant: Video với hook "3 giây — đủ để khách bỏ qua ads của bạn"

Giữ nguyên: Audience, budget, placement, landing page, CTA button
```

### Sample size và thời gian
- Tối thiểu **50-100 leads mỗi variant** để kết luận đáng tin cậy
- Chạy ít nhất **7 ngày** (tránh day-of-week bias)
- Dùng Facebook's built-in A/B test hoặc tạo manual split

---

## Reporting Framework

### Daily Check (5 phút)
- Spend vs budget pace (đang underdelivery không?)
- CPL/ROAS vs target ngày hôm qua
- Frequency tăng đột biến không?
- Có ad nào bị reject không?

### Weekly Review (30 phút)
1. Top/bottom performing ads → kill hoặc scale
2. Creative fatigue check (frequency + CTR trend)
3. Audience performance comparison
4. Budget reallocation: chuyển từ low-performer sang winner

### Monthly Report
- Tổng chi phí vs kết quả vs mục tiêu
- CAC (Customer Acquisition Cost) vs LTV
- Trend: CPL đang tăng hay giảm theo tháng?
- Kế hoạch creative và audience cho tháng tới

### Key Metrics Dashboard

| Metric | Công thức |
|--------|----------|
| CPL | Tổng chi phí / Số leads |
| CPA | Tổng chi phí / Số conversions |
| ROAS | Doanh thu / Chi phí quảng cáo |
| CTR | Clicks / Impressions × 100% |
| CVR | Conversions / Clicks × 100% |
| Frequency | Impressions / Reach |
| Hook Rate | 3-sec video views / Impressions × 100% |
| Hold Rate | ThruPlay / 3-sec views × 100% |
