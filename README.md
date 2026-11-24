# 专题展票价调整的可负担性与渠道核算

本项目保存视觉艺术机构日常业务分析使用的合成演练资料，样例不代表真实机构、作品、交易或研究结论。

## 资料

- `ticket_rules.csv`：票种资格、时段、渠道和有效价目，未给出最优方案。字段为 `rule_id, show_id, ticket_type, period, channel, base_price, discount_kind, discount_value, eligibility, valid_from, valid_to`。
- `sales.csv`：多渠道售票、退款及实际入账事件。字段为 `order_id, slot_id, channel, ticket_type, quantity, unit_price, discount, fee, order_state, ordered_at, refund_date`。
- `slot_context.csv`：场次日历、同期活动和可售容量。字段为 `slot_id, date, day_type, show_id, planned_capacity, access_seats, closure_state, other_event`。
- `audience_observations.csv`：访客构成及购票阻碍调查，未加权汇总。字段为 `response_id, period, visitor_group, purchase_state, price_band, visit_party, barrier, survey_source`。

记录之间通过 `*_id`、`*_key` 或 `*_ref` 字段关联。日期采用 ISO 格式；空值表示来源未提供该事实，不代表数值为零。不同来源的统计范围和状态以 `docs/data-contract.md` 为准。样例中保留了待确认、取消、缺失和版本变化等原始情况，不包含预先计算的分析结论。

## 运行

需要 Python 3.11 或更高版本，无第三方依赖。运行 `python3 -m unittest discover -s tests -v` 可检查资料编码、字段和记录结构。
