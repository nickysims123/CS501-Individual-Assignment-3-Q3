# Assignment 3 Q3 — Tag Browser

A single-screen tag browsing app built with Jetpack Compose and Material 3.

## Error Fix Disclosure

Initially, upon attempting to compile and preview the app on an android device, it will simply not run. The error states
that there is no static method "FlowRow". Once the versions of composeBom, activityCompose, and kotlin were updated,
the app is now able to run. 

## Materials Used

| Component | Where Used |
|---|---|
| `FlowRow` | Wraps tag `FilterChip` items across rows in the Browse Tags section; also used inside the Selected Tags card |
| `FlowColumn` | Stacks filter `AssistChip` items into multiple columns (`maxItemsInEachColumn = 3`) in the Filter by Category section |
| `FilterChip` | Each browsable tag; `selected` state toggles chip into/out of `selectedTags` set |
| `AssistChip` | Filter category chips in the `FlowColumn`; active filter highlighted via custom `assistChipColors()` |
| `Scaffold` | Root layout; provides `innerPadding` to offset content below system bars |
| `Surface` | Wraps the full content area inside `Scaffold` to apply the M3 surface colour |
| `Card` | Contains the Selected Tags area with an elevated surface |
| `Text` | Section headings and selected tag labels styled with `MaterialTheme.typography` |

## Modifiers Used

| Modifier | Where Used |
|---|---|
| `Arrangement.spacedBy()` | Outer `Column` (16 dp vertical), both `FlowRow`s and `FlowColumn` (8 dp horizontal + vertical) |
| `fillMaxWidth` | Applied to both `FlowRow`s, `FlowColumn`, `Card`, and `Surface` |
| `padding` | `16.dp` on root `Column`; `innerPadding` from `Scaffold`; `16.dp` inside card empty state |
| Visual selected state | `FilterChip` uses M3 built-in selected colours; `AssistChip` swaps to `primaryContainer` colour when active |
