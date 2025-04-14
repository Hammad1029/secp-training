## Prerequisites:

- Github CLI: https://cli.github.com/
- Java JDK >= 8
- Apache Maven
- Jenkins Jar: https://www.jenkins.io/download/

## 📅 Day 1: Foundations + Source Control + Issue Tracking + Build Tools (8 Hours)

### ⏰ Session 1: Introduction to CI/CD & DevOps (1 hour)

- What is DevOps? Key principles
- Introduction to CI/CD pipelines
- Importance of automation in modern software delivery
- Overview of the toolchain: Jira, Bitbucket, Git, Jenkins, Maven

### ⏰ Session 2: Jira for Agile Planning and Workflow Management (1.5 hours)

- Create Jira account, workspace, project (scrum template, team managed)
- Create issues
- Fill backlog and create a sprint
- Creating and managing boards (Sprint board)
- Create sprint board
- Integrating Jira with Bitbucket
- Create columns: developed, deployed
- Add rule: Project Settings > Automation > Create rule > Deployment successful
- Add Component → New action → Lookup issues → Add JQL script as “sprint IN openSprints()”.
- Add Component → New action → Transition issue → Set Destination status to Deployed.

### ⏰ Session 4: Maven for Build Automation (1.5 hours)

- Introduction to Maven
- Project Object Model (POM) explained
- Building a Java project using Maven
  - Generate project `mvn archetype:generate -DgroupId=com.example -DartifactId=tdd-example -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false`
  - Add dependencies:
    ```
    <dependencies>
      <dependency>
        <groupId>org.junit.jupiter</groupId>
        <artifactId>junit-jupiter-engine</artifactId>
        <version>5.7.0</version>
        <scope>test</scope>
      </dependency>
      <dependency>
        <groupId>org.junit.jupiter</groupId>
        <artifactId>junit-jupiter-api</artifactId>
        <version>5.7.0</version>
        <scope>test</scope>
      </dependency>
    </dependencies>
    ```
- Running unit tests: `mvn test`

### ⏰ Session 3: Git & Bitbucket for Source Control (2 hours)

- Create Bitbucket account
- Setup SSH
  - Generate: `ssh-keygen`
  - Add by: Settings dropdown menu > Personal Bitbucket Settings > Security > SSH keys > Add key
- Create a Bitbucket repository
- Clone repo
- Add maven project to repo using `cp -r *`
- Git fundamentals: stage, commit, push
- Setup pipeline
