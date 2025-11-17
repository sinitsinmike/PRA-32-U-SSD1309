# PRA-32-U-SSD1309
PRA-32-U with SSD1309 instead of SSD1306
##
	•	В .ino до #include "pra32-u-control-panel.h":
#

#define PRA32_U_SSD1309_USE_CHARGEPUMP_STYLE 1  // использовать 0x8D,0x14
#include "pra32-u-control-panel.h"

#
или в самом .h рядом с init SSD1309, заменив 0 на 1.
##
Быстрый тест:
	1.	Оставь normal_mode() закомментированным.
	2.	Если с 0x8D,0x14 не светится — переключи на 0xAD,0x8A.
	3.	При зеркале/перевороте поменяй 0xA1↔0xA0 и/или 0xC8↔0xC0.
	4.	Контраст (0x81, val) и precharge (0xD9, 0x22/0xF1) подбираются после выбора «pump».
