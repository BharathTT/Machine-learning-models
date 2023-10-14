# Real-time Sentiment Analysis
In the rapidly evolving landscape of the modern business world, it is imperative for organizations to effectively grasp and address customer feedback. As we navigate the digital age, managing real-time data presents both challenges and opportunities. This system is designed to facilitate the exploration of real-time sentiment analysis, a cutting-edge tool that empowers companies to leverage customer feedback and data-driven insights.

# Table of Contents:
 - Getting Started
 - Configuration & Usage
 - License
 - Authors & Contribution
 - Acknowledgement

# Getting Started:
To work with this project, ensure that your system meets the following requirements, which are shared between the two stacks:
- Operating System: Linux or macOS
- Python: Python 3.x
- Java: Java 11
- Apache Kafka: Installed and configured
- CPU: A multi-core CPU is recommended for parallel processing.
- Network Connection: A stable network connection is essential for data processing.

Additionally, please install the stack-specific libraries and tools as listed below:

Stack 1 (Additional Requirements):
- Python Libraries: Dash, Pyspark, NLTK, Vader, and other necessary Python libraries
- RAM: 8-16 GB of RAM is recommended for efficient performance.

Stack 2 (Additional Requirements):
- Python Libraries: pandas, pytorch, Dash, Hugging Face transformers, and other necessary Python libraries
- RAM: 4-8 GB of RAM is recommended for efficient performance.

Ensure your system meets both the common requirements and the stack-specific ones before proceeding with the installation and usage of this project. Detailed installation and usage instructions can be found in the relevant sections of this README.

# Configuration & Usage:

Before you can use this project, you need to set up and configure Apache Kafka as well as run the project's components. Follow these steps to get started:
1. **Kafka Setup**:
   - Download Apache Kafka from [Kafka Downloads](https://kafka.apache.org/downloads) and extract it.

   - Modify Kafka's `server.properties` file (usually found in `kafka/config`):
     ```plaintext
     advertised.listeners=PLAINTEXT://localhost:9092
     zookeeper.connect=localhost:2181
     ```

   - Start Zookeeper by executing the following command from the Kafka directory:
     ```
     ./bin/zookeeper-server-start.sh config/zookeeper.properties
     ```

   - Start Kafka with JMX enabled using the following command:
     ```
     JMX_PORT=8004 bin/kafka-server-start.sh config/server.properties
     ```

2. **CMAK Setup** (Optional):
   - Download CMAK (Confluent Control Center) from the [CMAK GitHub repository](https://github.com/yahoo/CMAK) or an appropriate source.

   - Navigate to the CMAK directory and clean the project:
     ```
     ./sbt clean dist
     ```

   - Unzip the CMAK zip file located in `./target/universal`.

   - Open the `application.conf` file located in `cmak/conf` and modify the following line:
     ```
     cmak.zkhosts="localhost:2181"
     ```

   - To run CMAK, use the following command from the CMAK directory:
     ```
     bin/cmak -Dconfig.file=conf/application.conf -Dhttp.port=8080
     ```

3. **Running the Project**:
   - Run the project's producer files located in the `producer` directory using the following commands:
     ```
     python3 ./producer/producer_news.py
     python3 ./producer/producer_red.py
     ```

   - Simultaneously, start the dashboard using the command:
     ```
     python3 ./dashboardLayout2.py
     ```

With these steps completed, your project is ready to work with Apache Kafka, CMAK (if needed), and the provided producer and dashboard components. Make sure all dependencies are correctly configured and running before launching the project components.


# Authors & Contribution:
Our Guides
 - Dr. Anupama Kumar
 - Epsilon Team 

Stack 1
 - Pratheek T M
 - Surya Prakash Reddy
 - Aravinda Kumar
   
Stack 2
 - Bharath GM
 - Mohammed Anas
 - Aradhya KC

# Acknowledgments:

> We extend our heartfelt gratitude to the Epsilon team, whose unwavering guidance and support played an instrumental role in the success of this project. Their expertise and dedication were invaluable in navigating the complexities of our undertaking.
We also wish to express our sincere appreciation to our department for their encouragement and resources that fueled our project's development. Their continuous support was a driving force behind our accomplishments.
A special mention and thanks go to our college guide, Anupama Mam, for her mentorship, encouragement, and invaluable insights throughout the project's journey. Her wisdom and guidance were pivotal in achieving our project's goals.
We are deeply thankful to everyone who contributed to this endeavor, and we look forward to building on these experiences in our future projects.

