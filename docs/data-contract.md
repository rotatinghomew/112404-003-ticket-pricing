# 合成资料约定

资料用于本地业务流程演练，字段仅记录事实来源，不预先裁定业务结果。

- `ticket_rules.csv`：票种资格、时段、渠道和有效价目，未给出最优方案。字段为 `rule_id, show_id, ticket_type, period, channel, base_price, discount_kind, discount_value, eligibility, valid_from, valid_to`。
- `sales.csv`：多渠道售票、退款及实际入账事件。字段为 `order_id, slot_id, channel, ticket_type, quantity, unit_price, discount, fee, order_state, ordered_at, refund_date`。
- `slot_context.csv`：场次日历、同期活动和可售容量。字段为 `slot_id, date, day_type, show_id, planned_capacity, access_seats, closure_state, other_event`。
- `audience_observations.csv`：访客构成及购票阻碍调查，未加权汇总。字段为 `response_id, period, visitor_group, purchase_state, price_band, visit_party, barrier, survey_source`。

空字段表示事实尚未提供，`pending`、`review`、`hold` 等状态表示来源记录尚未形成最终确认。不同来源以事件日期或有效期表达的时间含义不相同，调用方应结合表名和字段解释；不能仅因编号相同就假定两条记录可合并。金额以资料中记载的名义单位表示，没有统一换算或预先扣除退款。
