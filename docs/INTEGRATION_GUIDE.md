# 🔧 РУКОВОДСТВО ПО ИНТЕГРАЦИИ

## Как использовать систему в разных нейросетях

---

## 1. ChatGPT (OpenAI)

1. Откройте настройки → "Customize ChatGPT"
2. В поле "Instructions" вставьте содержимое `FULL_PROMPT.md`
3. Сохраните
4. Начните диалог — система активируется автоматически

---

## 2. Claude (Anthropic)

1. Создайте новый Project
2. В "Project Instructions" вставьте `FULL_PROMPT.md`
3. Или используйте API с system prompt

---

## 3. Kimi (Moonshot AI)

1. Используйте режим системного промпта
2. Вставьте `FULL_PROMPT.md` в поле системных инструкций
3. Система активируется при первом запросе

---

## 4. Google Gemini

1. В Gemini Advanced откройте настройки
2. Добавьте `FULL_PROMPT.md` в системные инструкции
3. Или используйте через Google AI Studio

---

## 5. Локальные модели (Ollama, LM Studio)

1. Запустите модель с системным промптом:
   ```bash
   ollama run llama3 --system "$(cat FULL_PROMPT.md)"
   ```
2. Или через LM Studio загрузите в System Prompt

---

## 6. API-интеграция

```python
import openai

system_prompt = open("FULL_PROMPT.md", "r", encoding="utf-8").read()

response = openai.ChatCompletion.create(
    model="gpt-4",
    messages=[
        {"role": "system", "content": system_prompt},
        {"role": "user", "content": "Ваш запрос здесь"}
    ]
)
```

---

## ⚠️ Важные замечания

1. **Полный промпт:** Для максимальной эффективности используйте `FULL_PROMPT.md` целиком
2. **Контекст:** Убедитесь, что модель поддерживает достаточный контекст (32K+ токенов)
3. **Тестирование:** Проверьте работу на простом запросе перед сложными задачами
4. **Обновления:** Следите за обновлениями в репозитории

---

**Автор:** Смолянинов Александр Вячеславович  
**Telegram:** @ASV_prod
