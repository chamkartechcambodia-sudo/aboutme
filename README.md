# About Me — Android Kotlin A5

**STEP IT Academy** — Android Mobile Application Development (Kotlin + XML UI)
> Day 5 — Layouts & Data Binding: LinearLayout, ScrollView, EditText, DataBinding

---

## Screenshots

![Screenshot](screenshots/AboutMeScreenshots.png)

---

## About

**About Me** là app demo hiển thị thông tin cá nhân của một người:
- Tên (từ data class `MyName`)
- Nickname (nhập bằng `EditText`, lưu qua DataBinding hai chiều)
- Ảnh đại diện
- Bio có thể cuộn (`ScrollView`)

Khi nhấn **Done**, nickname được lưu vào data class qua two-way binding (`@={}`), `EditText` và Button ẩn đi, `TextView` nickname hiện lên.

---

## Architecture

- Pattern: **Single Activity + DataBinding**
- Data class `MyName` làm model đơn giản
- `DataBindingUtil.setContentView()` bind layout với Activity
- Two-way binding `@={}` đồng bộ `EditText` ↔ `MyName.nickname`

```
MainActivity
    └── binding: ActivityMainBinding (DataBinding)
            └── myName: MyName (data class)
                    ├── name: String
                    └── nickname: String
```

---

## Project Structure

```
app/src/main/
├── java/com/example/android/aboutme/
│   ├── MainActivity.kt        ← setContentView + click handler
│   └── MyName.kt              ← data class (name, nickname)
└── res/
    ├── layout/
    │   └── activity_main.xml  ← <layout> root, two-way binding
    ├── values/
    │   ├── strings.xml
    │   ├── colors.xml
    │   ├── dimens.xml
    │   └── styles.xml
    └── font/
        └── roboto.ttf
```

---

## Tech Stack

| Library | Version |
|---|---|
| AndroidX AppCompat | 1.7.1 |
| AndroidX Core KTX | 1.18.0 |
| Material Components | 1.13.0 |
| ConstraintLayout | 2.2.1 |
| DataBinding | bundled với AGP |

---

## Build Requirements

| Tool | Version |
|---|---|
| Android Gradle Plugin | 9.0.1 |
| Gradle | 9.2.1 |
| JDK | 21 |
| Min SDK | 24 |
| Target SDK | 36 |
| Compile SDK | 36 |

**JDK Setup:** `File → Settings → Build Tools → Gradle → Gradle JDK` → chọn **Embedded JDK**

---

## Exercise Steps

| Step | Branch | Nội dung |
|---|---|---|
| 01 | `Step.01-Exercise-Create-layout-file` | Tạo layout file cơ bản |
| 01 | `Step.01-Solution-Create-layout-file` | Solution |
| 02 | `Step.02-Exercise-Add-TextView-ImageView-Style` | Thêm TextView, ImageView, Style |
| 02 | `Step.02-Solution-Add-TextView-ImageView-Style` | Solution |
| 03 | `Step.03-Exercise-Add-ScrollView` | Thêm ScrollView cho bio |
| 03 | `Step.03-Solution-Add-ScrollView` | Solution |
| 04 | `Step.04-Exercise-EditText-DoneButton-ClickHandler` | EditText + Button + click handler |
| 04 | `Step.04-Solution-EditText-DoneButton-ClickHandler` | Solution |
| 05 | `Step.05-Exercise-Implement-data-binding` | Triển khai DataBinding |
| 05 | `Step.05-Solution-Implement-data-binding` | Solution |

### Cách làm bài

```bash
# Checkout branch exercise
git checkout Step.XX-Exercise-Topic

# Tìm và hoàn thành các TODO trong code
# (Android Studio → View → Tool Windows → TODO)

# So sánh với solution
git diff Step.XX-Exercise-Topic Step.XX-Solution-Topic
```

---

## Course Info

- **Academy:** STEP IT Academy Cambodia
- **Instructor:** Magn
- **Org:** [chamkartechcambodia-sudo](https://github.com/chamkartechcambodia-sudo)
- **Course:** Android Kotlin — Batch 1
