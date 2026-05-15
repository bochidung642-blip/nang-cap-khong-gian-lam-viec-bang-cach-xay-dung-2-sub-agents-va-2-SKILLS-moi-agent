# 2 Sub-Agents & Skills — Claude Code

> Không gian làm việc gồm 2 sub-agents chuyên biệt, mỗi agent được trang bị bộ SKILLS riêng để tự động hoá công việc marketing.

---

## Tổng quan kiến trúc

```mermaid
mindmap
  root((".claude/"))
    agents/
      content-social-media
      technical-facebook-ads
    skills/
      content-social-media/
        hooks.md
        copywriting-frameworks.md
        platform-guidelines.md
        content-strategy.md
      facebook-ads/
        meta-ads.md
        tracking-setup.md
        campaign-optimization.md
```

---

## Agents & Skills

```mermaid
graph LR
    subgraph A1["Agent 1 — content-social-media"]
        direction TB
        R1["Senior Content Strategist & Copywriter<br/>Facebook · Instagram · TikTok · LinkedIn"]
    end

    subgraph A2["Agent 2 — technical-facebook-ads"]
        direction TB
        R2["Senior Facebook Ads Specialist<br/>Meta Ads · Pixel · CAPI · Optimization"]
    end

    subgraph SK1["Skills / content-social-media/"]
        direction TB
        H["hooks.md<br/>7 loại hook + công thức"]
        C["copywriting-frameworks.md<br/>AIDA · PAS · BAB · FAB · PASTOR · 4U"]
        P["platform-guidelines.md<br/>Thuật toán & best practices 4 nền tảng"]
        S["content-strategy.md<br/>Pillars · Calendar · KPIs · Repurposing"]
    end

    subgraph SK2["Skills / facebook-ads/"]
        direction TB
        M["meta-ads.md<br/>Campaign · Audience · Bidding · Learning Phase"]
        T["tracking-setup.md<br/>Pixel · CAPI · GTM · UTM · Checklist"]
        O["campaign-optimization.md<br/>Diagnose · Scale · A/B Test · Reporting"]
    end

    A1 -- đọc --> SK1
    A2 -- đọc --> SK2
```

---

## Kết quả thực chiến

> **Case study:** Khóa học tiếng Anh giao tiếp cho người đi làm (fanpage Facebook)

```mermaid
graph TD
    INPUT["Yêu cầu: Tạo kế hoạch marketing 30 ngày"]

    INPUT --> AGT1["content-social-media agent"]
    INPUT --> AGT2["technical-facebook-ads agent"]

    AGT1 --> OUT1["📄 outputs/english-course-content-30days.md<br/>30 bài POST-01 → POST-30"]

    OUT1 --> L["🔵 Phễu Lạnh — POST-01→10<br/>Awareness | CTA nhẹ<br/>Bài viết · Poll · Video tips"]
    OUT1 --> W["🟡 Phễu Ấm — POST-11→22<br/>Consideration | CTA trung<br/>Case study · FAQ · Demo · Testimonial"]
    OUT1 --> H["🔴 Phễu Nóng — POST-23→30<br/>Conversion | CTA mạnh<br/>Offer · Urgency · Objection · Close"]

    AGT2 --> OUT2["📊 outputs/english-course-facebook-ads-plan.md<br/>3 Campaigns · 11 Ad Sets · 6 Tình huống tối ưu"]

    OUT2 --> C1["C1 AWARENESS<br/>Objective: Video Views<br/>4 Ad Sets · Cold audience"]
    OUT2 --> C2["C2 CONSIDERATION<br/>Objective: Leads<br/>4 Ad Sets · Warm audience"]
    OUT2 --> C3["C3 CONVERSION<br/>Objective: Leads High Intent<br/>3 Ad Sets · Hot audience"]

    L -. creative .-> C1
    W -. creative .-> C2
    H -. creative .-> C3
```

### Ngân sách đề xuất

| Mức | Tổng 30 ngày | CPL mục tiêu | Leads dự kiến |
|-----|-------------|--------------|--------------|
| Nhỏ | 15 triệu VND | 50K – 150K | 100 – 300 |
| Trung | 45 triệu VND | 80K – 200K | 225 – 562 |
| Lớn | 90 triệu VND | 100K – 250K | 360 – 900 |

---

## Cài đặt vào Claude Code

```bash
cp -r .claude/agents/* ~/.claude/agents/
cp -r .claude/skills/* ~/.claude/skills/
```

