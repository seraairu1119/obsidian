---

tags:

  - ES

  - 文章ルール

source:

  - 就活CODEX/skills/personal-es-profile/SKILL.md

  - 就活CODEX/skills/interview-self-analysis/SKILL.md

  - 就活CODEX/skills/es-writing-rules/SKILL.md

---



# ES作成ルール



# ES Writing Rules



## Overall Balance



- Check balance with other questions in the same ES when multiple prompts are provided.

- Avoid repeating the same content in the same ES.

- Avoid repeating the same fact, background, purpose, issue, action, or result within a single answer.

- If the same information must be mentioned again, write it as a continuation or implication of the earlier mention, such as `この課題に対して`, `その結果`, `この経験から`, or `上記の取り組みを通じて`, instead of explaining it again from the beginning.

- It is acceptable to use the same broad topic if the episode, angle, or emphasized learning is different.

- Prefer assigning each major episode a clear role:

  - 長期インターン: 顧客課題、提案、成果、SE志望、就活の軸。

  - アカペラ: チーム経験、巻き込み、リーダーシップ、困難克服。

  - 研究・データ分析: 学業、研究内容、分析力、IT・データ活用。

  - イラスト・謎解き: 趣味、特技、対話力、協働して答えを導く姿勢。



## Character Count



- Measure character count with a Python function when a character limit is specified.

- Count full-width characters as `1`.

- Count half-width characters as `0.5`.

- Count spaces, line breaks, punctuation, and Japanese punctuation as `0.5`.

- Aim for at least 90% of the specified character limit.

- If the draft is under 90%, expand with concrete actions, results, or motivation.

- If the draft exceeds the limit, reduce explanation before removing core evidence.



Use this counting logic:



```python

import unicodedata

映画が誕生してから	

1.映像の歴史	A

2.フィルムよりも	C

3.フィルム映画	C



def es_len(text: str) -> float:

    total = 0.0

    for char in text:

        if char in {" ", "\n", "\t", "。", "、", "，", "．", "！", "？"}:

            total += 0.5

        elif unicodedata.east_asian_width(char) in {"F", "W", "A"}:

            total += 1.0

        else:

            total += 0.5

    return total

```



## Writing Style



- Write every answer conclusion-first.

- Make the first sentence answer the question directly.

- Use concrete evidence before abstract traits.

- Do not restate the same point in different wording just to increase character count. Add new concrete actions, results, reasons, or learning instead.

- Avoid ending with a vague virtue only. Tie the conclusion to work, learning, or the company when relevant.

- Keep tone natural, specific, and businesslike.

- Keep sentences concise but natural. Avoid cramming many clauses into one long sentence, but do not chop everything into very short staccato sentences either. Aim for a natural rhythm: mix medium-length sentences with shorter ones, and use connectives (`また`, `そのため`, `一方で`, `その結果`) where they make the flow read smoothly. A good target is roughly 40-70 characters per sentence on average. One main point per sentence is a guideline, not a hard rule; combine closely related points when splitting them would feel unnatural.

- Write in plain form (だ・である調), not polite form (です・ます調). Use endings such as `である`, `だ`, `と考える`, `に取り組んだ`, `を実感した`. Do not mix the two styles within an answer.



## Recommended Structure



Use the following 6-step structure when it improves clarity. It is not mandatory if the character limit is too short.



1. 結論

2. 理由

3. 目標 / 課題

4. 具体的な行動

5. 結果

6. 再度結論（学び・まとめ）



## Output Format



- When drafting answers, include the final answer and the measured character count.

- When multiple drafts are useful, provide 2-3 variants with different angles.

- When revising, preserve the user's facts and improve structure, specificity, and fit to the prompt.

- Do not invent achievements, company facts, grades, awards, or numeric results.



## Factual Accuracy (Strict)



- Do not write anything in an ES that may differ from fact. Only state what the user has actually done, thought, felt, or studied.

- Do not embellish or reframe the user's mindset. For example, do not claim the user "saw a difference as a strength" (`違いを強みと捉え`) or "felt motivated by X" unless the user actually said so. Describe the user's real intent instead of inventing a flattering interpretation.

- Do not upgrade secondhand, estimated, or uncertain results into definite facts beyond how the user states them.

- Use the user's exact factual details. Do not mislabel them, for example a 学科 (department) is not a 専攻 (major/field). State the 専攻 / research field exactly as the user gives it.

- When unsure whether a detail is accurate, leave it out or ask the user. Prefer omission over a plausible-but-unverified claim.

