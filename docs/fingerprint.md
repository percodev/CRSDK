# Работа с отпечатками пальца

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
  // Финал, получаем изображение отпечатка и шаблон отпечатка
  if (cmd == CR_RESULT) ...
}
```

## Структуры


