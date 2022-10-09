# WAF

## WAFとは？

- AWSの提供するファイアーウォール
- 以下AWSサービスのHTTP(s)リクエストを監視
    - CloudFront
    - API Gateway
    - ALB
    - AppSync

## 基本構造

階層：WAF > ACLs > Rules > Conditions

- WAF
    - ACL 1
        - Rule 1.1
            - Condition 1.1.1
            - Condition 1.1.2
        - Rule 1.2
            - Condition 1.2.1
    - ACL 2

Conditions: IPアドレス、SQLインジェクションなどの具体的な条件

# 参考URL

[AWS WAF 解説 【第1回 基本構造編】 | WafCharm（ワフチャーム） - AWS / Azure /Google CloudのWAF自動運用サービス](https://www.wafcharm.com/blog/aws-waf-basic-structure/)
