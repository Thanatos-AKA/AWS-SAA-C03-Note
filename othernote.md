類型	關鍵字 / 應用場景	運作原理

Cluster (叢集)	HPC (高效能運算)、Low Latency (低延遲)、High Throughput (高吞吐量)	把機器全部塞在同一個機櫃 (Rack) 裡。因為物理距離最近，網路跑得最快。(風險：機櫃壞了全部一起死，不適合高可用性)

Spread (分散)	Critical Application、High Availability、不同硬體	強制把機器分開放在不同的機櫃，甚至不同的機房。確保「雞蛋不要放在同一個籃子裡」。(限制：每個 AZ 最多只能放 7 台)

Partition (分割)	Hadoop, Kafka, Cassandra, Big Data	把機器分成幾小群 (Partitions)。群組 A 壞了不會影響群組 B。適合分散式大數據運算。

---

Question: You have a backend application that processes messages from an SQS queue. The processing of each message takes about 5 minutes. However, you notice that while one server is processing a message, the same message reappears in the queue after 30 seconds and is picked up by another server, causing duplicate processing. What parameter should you change to fix this? (後端處理一個訊息要 5 分鐘。但你發現過了 30 秒，同一個訊息又跑回佇列被別人拿去處理，導致重複做工。該調哪個參數？)

(A) Increase the Message Retention Period (增加訊息保留期間). (B) Increase the Visibility Timeout (增加能見度逾時). (C) Enable Long Polling (開啟長輪詢). (D) Use a FIFO Queue (使用先進先出佇列).

---

Question: You have three VPCs: VPC A, VPC B, and VPC C.

VPC A is peered with VPC B. (A <-> B)

VPC B is peered with VPC C. (B <-> C) You want instances in VPC A to communicate with instances in VPC C. (A 和 B 有連線，B 和 C 有連線。請問 A 可以直接連到 C 嗎？)

(A) Yes, traffic will automatically route through VPC B. (可以，流量會自動經過 B 轉送) (B) Yes, but you need to update the Route Tables in A, B, and C to allow the traffic. (可以，但要改一下路由表) (C) No, transitive peering is not supported. You must create a new peering connection between VPC A and VPC C. (不行，VPC Peering 不支援過路轉送。A 和 C 必須另外拉一條線) (D) No, you must use a NAT Gateway in VPC B to forward the traffic.

---

Question: By default, when an EBS-backed EC2 instance is terminated, what happens to the Root Volume (/dev/sda1)? (預設情況下，當 EC2 被終止/刪除時，根磁碟區會發生什麼事？)

(A) It is saved as a Snapshot. (B) It is detached and preserved (Data remains). (C) It is deleted automatically (Data is lost). (D) It is converted to an Instance Store volume.
