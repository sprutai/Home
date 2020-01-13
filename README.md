# Sprut.Home

![Home](https://github.com/sprut/Home/blob/master/Home.jpg)


## Изменения

### 1.0 (53)

#### Feature
1. Добавлено отображение названия комнаты на кнопку устройства при просмотре дома

#### Bugfix
1. Исправлен баг с минимальными и максимальными значениями в карточке дома
2. Исправлен баг с отрицательным значениями температур

### 1.0 (52)

#### Feature
1. Добавлены сервисы: MicrophoneService SpeakerService, AirPurifierService, FaucetService, Carbon Monoxide Sensor, Occupancy Sensor
2. Добавлена поддержка LockPhysicalControls, SwingMode, TargetState для Fan2
3. Статусные иконки справа от имени будут отображаться теперь только если они добавлены в избранное

#### Bugfix
1. Исправлен порядок очередности иконок справа от имени в порядке их появления, справа налево

### 1.0 (51)

#### Feature
1. Возможность менять порядок комнат в доме
2. Возможность добавления новой комнаты
3. Возможность редактирования дома и комнаты
3. Возможность удаления комнаты
4. Возможность скрытия комнаты
5. Добавлены сервисы VentilationFanService (fan v2), AtmosphericPressureSensor, NoiseSensor, VoltMeter, AmpereMeter, WattMeter, VoltAmpereMeter, KilowattHourMeter, KilowattVoltAmpereHourMeter
6. Обновлен сервис FanService
7. В детальном отображении комнаты изменены местами датчики и устройства. Датчики теперь идут первые.
8. Теперь датчики, сенсоры, температура и прочие отображаются только если добавлены в изобранное.
9. Переделана логика подписок на характеристики устройств
10. Добавлено отображение серийного номера устройства

#### Bugfix
1. Исправлено отображение длинного название комнаты в настройках устройства
2. Исправлен баг с добавлением, удалением устройством в избранное
3. Улучшено отображение иконок
4. Исправлено отображение показа статуса устройства с типом розетка

### 1.0 (39)

1. Добавлены картинки для комнат: Детская, Огород
2. Переделаны экраны просмотра дома и комнаты, добавлена возможность сменить название

### Дополнительные типы,

#### Сервисы:

	C_AccessoryExtInfo(
			"00000001-6666-6666-6666-666666666666", //
			l(C_Room.class), // Required
			l(Name.class) // Optional
	),
	C_AtmosphericPressureSensor(
			"00000003-6666-6666-6666-666666666666", //
			l(C_CurrentAtmosphericPressure.class), // Required
			l(Name.class) // Optional
	),
	C_NoiseSensor(
			"00000005-6666-6666-6666-666666666666", //
			l(C_NoiseDetected.class), // Required
			l(Name.class, C_CurrentNoiseLevel.class) // Optional
	),
	C_VoltMeter(
			"00000008-6666-6666-6666-666666666666", //
			l(C_Volt.class), // Required
			l(Name.class) // Optional
	),
	C_AmpereMeter(
			"00000009-6666-6666-6666-666666666666", //
			l(C_Ampere.class), // Required
			l(Name.class) // Optional
	),
	C_WattMeter(
			"00000010-6666-6666-6666-666666666666", //
			l(C_Watt.class), // Required
			l(Name.class) // Optional
	),
	C_VoltAmpereMeter(
			"00000011-6666-6666-6666-666666666666", //
			l(C_VoltAmpere.class), // Required
			l(Name.class) // Optional
	),
	C_KilowattHourMeter(
			"00000012-6666-6666-6666-666666666666", //
			l(C_KilowattHour.class), // Required
			l(Name.class) // Optional
	),
	C_KilowattVoltAmpereHourMeter(
			"00000013-6666-6666-6666-666666666666", //
			l(C_KilowattVoltAmpereHour.class), // Required
			l(Name.class) // Optional

      
#### Характеристики:
	HC(String id, boolean read, boolean write, boolean notify, String format, Float min, Float max, Float step, Integer length, String unit, String valid)

	C_Room("00000002-6666-6666-6666-666666666666", true, true, true, "string", null, null, null, 64, null, null),
	C_CurrentAtmosphericPressure("00000004-6666-6666-6666-666666666666", true, false, true, "float", 0f, 2000f, 1.0f, null, "mmHg", null),
	C_CurrentNoiseLevel("00000006-6666-6666-6666-666666666666", true, false, true, "float", 0f, 200f, 1.0f, null, "dB", null),
	C_NoiseDetected("00000007-6666-6666-6666-666666666666", true, false, true, "uint8", 0.0f, 1.0f, 1.0f, null, null, "0,1"), // {"0":"levels are normal","1":"levels are abnormal"}
	C_Volt("00000014-6666-6666-6666-666666666666", true, false, true, "float", 0f, 65535f, 1.0f, null, "V", null),
	C_Ampere("00000015-6666-6666-6666-666666666666", true, false, true, "float", 0f, 65535f, 1.0f, null, "A", null),
	C_Watt("00000016-6666-6666-6666-666666666666", true, false, true, "float", 0f, 65535f, 1.0f, null, "W", null),
	C_VoltAmpere("00000017-6666-6666-6666-666666666666", true, false, true, "float", 0f, 65535f, 1.0f, null, "VA", null),
	C_KilowattHour("00000018-6666-6666-6666-666666666666", true, false, true, "float", 0f, 65535f, 1.0f, null, "kWh", null),
	C_KilowattVoltAmpereHour("00000019-6666-6666-6666-666666666666", true, false, true, "float", 0f, 65535f, 1.0f, null, "kVAh", null);
