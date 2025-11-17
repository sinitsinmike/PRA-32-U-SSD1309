Triple-controller header (SSD1306 / SH1106 / SSD1309)
====================================================
Switch controller (open header, top section):
  #define PRA32_U_OLED_IS_SH1106 1   // default now
  // #define PRA32_U_OLED_IS_SSD1306 1
  // #define PRA32_U_OLED_IS_SSD1309 1

Offsets:
- SSD1306: PRA32_U_OLED_SSD1306_X_OFFSET (default 0)
- SH1106 : PRA32_U_OLED_SH1106_X_OFFSET  (default 4)
- SSD1309: PRA32_U_OLED_SSD1309_X_OFFSET (default 0)

What changed:
- set_draw_position(): uses PRA32_U_OLED_X_OFFSET; auto-clears left margin when offset>0
- line_tail(y): sets column 126+offset and writes two zeros
- optional SSD1309 init helper: PRA32_U_ControlPanel_init_display_SSD1309()

All original functions remain intact.
