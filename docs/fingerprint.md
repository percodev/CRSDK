# Работа с отпечатками пальца

Полученное изображение передается в формате Base64. 
Вернутся [назад](https://percodev.github.io/CRSDK) для ознакомления с другими возможностями.


## Методы

```c++
// Запустить считывание отпечатка пальца
int cr_fingerprint_start_scan(callback, context)
```

* callback - Обработка получаемых событий из сканера
* context - Пользовательский контекст

```c++
// Остановить считывание отпечатка пальца
int cr_fingerprint_cancel_scan()
```

## Обработка событий 

```c++
void callback(CRFingerprintCommand cmd, CRFingerprintParams params, void* context)
{
  // Получаем сообщения от сканера
  if (cmd == CR_CMD) ...
  // Получаем снимки отпечатка, пока идет сканирование
  else if (cmd == CR_IMAGE_PROCESSED) ...
  // Получаем изображение отпечатка и шаблон отпечатка
  else if (cmd == CR_RESULT) ...
  // Устройство завершило сканирование отпечатка
  else if (cmd == CR_CLOSED) ...
}
```

## Структуры

```c++
enum CRFingerprintCommand
{
    CR_CMD,
    CR_IMAGE_PROCESSED,
    CR_RESULT,
    CR_CLOSED
};
```

