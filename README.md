## gotcha-api

# Architecture Diagram
Architecture diagram:

            +----------------------------------------+
            |                Client                  |
            +-------------------+--------------------+
                                |
                                v
            +-------------------+--------------------+
            |                API Gateway             |
            +-------------------+--------------------+
                                |
                                v
      +--------+----------+---------+----------+------------+
      |        |                |                |          |
      |        v                v                v          |
      |  Microservice 1  Microservice 2    Microservice N   |
      |     (ASP.NET)      (ASP.NET)          (ASP.NET)     |
      |        |                |                |          |   
      |        v                v                v          |
      |      Entity           Entity           Entity       |
      |    Framework         Framework        Framework     |
      |        |                |                |          |
      |        v                v                v          |
      |     Database         Database         Database      |
      |        |                |                |          |
      |        v                v                v          |
      |      RabbitMQ        RabbitMQ         RabbitMQ      |
      |        |                |                |          |
      |        v                v                v          |
      |      Pub/Sub         Pub/Sub          Pub/Sub       |
      |      (MediaTR)      (MediaTR)        (MediaTR)      |
      +--------+----------+---------+----------+------------+
                                |
                                v
                              Docker
                                |
                                v
                       +------------------+
                       |  Docker Compose  |
                       +------------------+
