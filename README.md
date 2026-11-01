<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/header-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/header-light.svg">
  <img alt="Saransh Singh - Software Engineer" src="assets/header-dark.svg" width="100%">
</picture>

<br><br>

<p align="center">
  <a href="https://sars-23.github.io/Portfolio/"><img src="https://img.shields.io/badge/Live%20Portfolio-sars--23.github.io-f59e0b?style=for-the-badge&logo=googlechrome&logoColor=white&labelColor=0d1117" alt="Portfolio Badge"></a>
  <a href="https://github.com/sars-23/Amber_Project"><img src="https://img.shields.io/badge/Flagship-Amber%20DSP-38bdf8?style=for-the-badge&logo=github&logoColor=white&labelColor=0d1117" alt="Amber Project"></a>
  <a href="mailto:saransh.9822@gmail.com"><img src="https://img.shields.io/badge/Direct%20Email-saransh.9822-10b981?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0d1117" alt="Email Badge"></a>
</p>

</div>

---

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/section-about.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/section-about-light.svg">
  <img alt="About Me" src="assets/section-about.svg" width="100%">
</picture>

I am a Computer Science undergraduate at **JECRC University (2023–2027)** focused on backend engineering, Java systems architecture, and first-principles software design.

Rather than treating modern frameworks and external libraries as opaque abstractions, I enjoy deconstructing complex systems to their mathematical and computational foundations. Whether engineering a custom Cooley–Tukey Fast Fourier Transform (FFT) for audio fingerprinting, implementing a handwritten recursive-descent compiler interpreter, or structuring isolated container execution sandboxes, my goal is always the same: **understand the system from first principles and build robust, deterministic software.**

```java
import java.util.List;

public record DeveloperIdentity(
    String engineer,
    String academicDegree,
    String institutionalAffiliation,
    String corePhilosophy,
    List<String> activeFocusAreas
) {
    public static final DeveloperIdentity SARANSH = new DeveloperIdentity(
        "Saransh Singh",
        "B.Tech in Computer Science & Engineering (2023–2027)",
        "JECRC University, Jaipur",
        "Understand foundational mechanics; engineer deterministic systems.",
        List.of(
            "Java 21 & Spring Boot 3 Backend Systems",
            "Full-Stack Web Architecture & Real-Time Streams",
            "Digital Signal Processing & Algorithmic Audio Search",
            "Compiler Frontends & Abstract Syntax Tree Interpreters",
            "Relational Schema Design & B-tree Index Optimization"
        )
    );
}
```

---

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/section-projects.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/section-projects-light.svg">
  <img alt="Featured Projects" src="assets/section-projects.svg" width="100%">
</picture>

### 👑 Amber — Real-Time Acoustic Fingerprinting & Music Recognition Platform

> **Flagship Engineering Project** • *Engineered from first principles in Java 21, Spring Boot 3, and React 19 without third-party recognition APIs or numerical math packages.*

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/amber-pipeline-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="assets/amber-pipeline-light.svg">
    <img alt="Amber Signal Pipeline" src="assets/amber-pipeline-dark.svg" width="100%">
  </picture>
</div>

<br>

Amber is a full-stack acoustic fingerprinting and audio identification system capable of recognizing music in real time through a browser microphone or uploaded audio file. Instead of delegating recognition to proprietary cloud APIs, Amber executes an end-to-end discrete digital signal processing pipeline:

* **Custom Radix-2 Cooley–Tukey FFT & STFT Framing:** Transforms incoming continuous time-domain PCM samples into frequency-domain spectral slices using sliding Hann windows, decomposing raw audio across discrete frequency bins.
* **Combinatorial Constellation Hashing:** Extracts local magnitude peaks within logarithmic frequency intervals and generates compact 32-bit hashes `[f1:f2:Δt]` by pairing anchor points with target peaks inside a forward time-frequency bounding box.
* **PostgreSQL B-tree Indexed Candidate Retrieval:** Evaluates query fingerprint hashes against indexed reference fingerprints via PostgreSQL B-tree lookups to retrieve candidate track recordings with low latency.
* **Time-Coherent Offset Histogram Matching & Five-Gate Acceptance:** Computes offset deltas `(t_track - t_query)` across candidate hashes. Production recognition isolates true matches via an offset histogram coherence peak subjected to a strict five-gate acceptance pipeline (minimum peak votes, coherence score, coherence ratio, ambiguity margin, and confidence thresholds) to eliminate false positives.
* **Browser Microphone Streaming via AudioWorklet:** Continuously samples live input at 11,025 Hz using a native client-side AudioWorklet downsampler with polyphase FIR filtering and WebSockets transport.
* **Isolated In-Memory Noise Lab Benchmark:** Features a self-contained in-memory benchmarking suite that injects deterministic synthetic noise (additive Gaussian noise at configurable SNR dB levels) to evaluate algorithmic degradation in isolation. Unlike the production matcher, the Noise Lab evaluator runs entirely without database persistence or the five-gate production acceptance pipeline, providing focused unit-level DSP diagnostics.

<p align="left">
  <a href="https://amber-frontend-w78m.onrender.com"><b>🌐 Live Production Application</b></a> &nbsp;•&nbsp;
  <a href="https://github.com/sars-23/Amber_Project"><b>📦 GitHub Source Repository</b></a> &nbsp;•&nbsp;
  <a href="https://sars-23.github.io/Portfolio/"><b>📑 Architecture Case Study</b></a>
</p>

---

### 🌿 Arbor — Dynamically Typed Programming Language Interpreter

> **Compiler Architecture & Systems** • *Java • Lexical Scanner • Recursive-Descent Parser • AST Visitor Pattern • Swing Mini-IDE*

Arbor is an interpreted programming language implemented in Java, featuring a custom lexer, parser, and tree-walk evaluation runtime:

* **Handwritten Lexical Scanner:** Implemented without parser generators (such as ANTLR or Flex), streaming tokens while maintaining line and column source mappings for precise syntax error reporting.
* **Recursive-Descent Parser:** Translates token streams into an Abstract Syntax Tree (AST) supporting operator precedence, nested expressions, variable declarations, and control flow constructs.
* **Tree-Walk Evaluation Engine:** Utilizes the Visitor Pattern to traverse AST nodes with support for lexical scoping, environment stacking, and first-class closures.
* **Integrated Developer Environment:** Includes a lightweight Java Swing mini-IDE featuring syntax highlighting, live token inspection, and an interactive execution REPL.

*Status: Private codebase. Formal grammar specifications and execution models are documented on the [portfolio website](https://sars-23.github.io/Portfolio/).*

---

### 🌰 Project Apricorn — Developer Growth & Practice Engine

> **Backend Architecture & Execution Sandboxing** • *Java 21 • Spring Boot • Docker • PostgreSQL • Flyway*

A developer practice platform designed to evaluate and guide programmatic problem-solving progression:

* **Docker Execution Sandbox:** Executes untrusted code inside isolated ephemeral containers with strict CPU time quotas, memory bounds, and disabled network access.
* **Solution Journey Progression:** Tracks iterative code attempts over time, providing granular historical snapshots and deterministic insights into developer refinement patterns.
* **Database Persistence:** Managed through Flyway schema migrations, backed by PostgreSQL relational models for user submissions, problem test fixtures, and telemetry.

*Status: Private codebase. Full architectural overview and interface designs are documented on the [portfolio website](https://sars-23.github.io/Portfolio/).*

---

### 📇 Java Contact Management System

> **Object-Oriented Design & Desktop Application** • *Java • Java Swing • In-Memory Data Structures*

A desktop CRUD management application built with Java Swing and custom in-memory data structures:

* **Average $O(1)$ In-Memory Indexing:** Backed by a `LinkedHashMap<String, Contact>` providing average $O(1)$ key lookup, insertion, update, and deletion operations while preserving the user's insertion order.
* **Field Validation Logic:** Validates required non-empty first and last names, enforces standard email format via regex, and verifies that phone numbers contain at least 10 digits. Addresses are optional and trimmed without custom format validation.
* **Desktop Swing Architecture:** Encapsulates business models (`Contact`, `ContactManager`) cleanly from the Swing graphical interface (`ContactManagementGUI`).

<p align="left">
  <a href="https://github.com/sars-23/Java_Contact_Management_System"><b>📦 GitHub Source Repository</b></a>
</p>

---

### 👁️ Real-Time Drowsiness Detection Prototype

> **Computer Vision & Geometric Modeling** • *Python • OpenCV • MediaPipe Face Mesh*

An experimental computer-vision prototype exploring facial landmark extraction and geometric threshold analysis:

* **468-Point Facial Mesh:** Utilizes MediaPipe Face Mesh to extract normalized facial coordinate landmarks from live webcam frames.
* **Frame-Level Eye Aspect Ratio (EAR):** Computes the Euclidean distance ratio across eye landmark pairs; when the instantaneous EAR falls below a configurable threshold (default `0.25`), the prototype renders an on-screen `"DROWSY!"` visual warning.
* **Frame-Level Mouth Aspect Ratio (MAR):** Computes the Euclidean vertical-to-horizontal lip landmark ratio; when instantaneous MAR exceeds the threshold (default `0.5`), it overlays a `"YAWNING!"` visual warning.

*Note: Developed strictly as an experimental educational prototype for frame-level geometric landmark analysis without temporal state tracking, blink duration counters, or validated automotive safety certification.*

<p align="left">
  <a href="https://github.com/sars-23/real-time-drowsiness-detection"><b>📦 GitHub Source Repository</b></a>
</p>

---

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/section-stack.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/section-stack-light.svg">
  <img alt="Technical Arsenal" src="assets/section-stack.svg" width="100%">
</picture>

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://skillicons.dev/icons?i=java,python,cpp,ts,js,spring,react,postgres,mysql,docker,maven,git,github,vscode&theme=dark">
    <source media="(prefers-color-scheme: light)" srcset="https://skillicons.dev/icons?i=java,python,cpp,ts,js,spring,react,postgres,mysql,docker,maven,git,github,vscode&theme=light">
    <img src="https://skillicons.dev/icons?i=java,python,cpp,ts,js,spring,react,postgres,mysql,docker,maven,git,github,vscode&theme=dark" alt="Technical Arsenal Icons" />
  </picture>
</div>

<br>

| Category | Primary Technologies &amp; Tooling |
| :--- | :--- |
| **Languages** | Java (21 LTS), Python, C++, TypeScript, JavaScript, SQL |
| **Backend &amp; Runtimes** | Spring Boot 3, Spring MVC, REST APIs, WebSockets, AudioWorklet Streams |
| **Frontend &amp; UI** | React 19, TypeScript, HTML5, CSS3, Tailwind CSS, Java Swing |
| **Databases &amp; Storage** | PostgreSQL (B-tree Indexing), MySQL, In-Memory Storage (`LinkedHashMap`) |
| **Tools &amp; Infrastructure** | Git, GitHub, Docker, Apache Maven, VS Code, FFmpeg, Render |

---

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/section-focus.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/section-focus-light.svg">
  <img alt="Current Focus" src="assets/section-focus.svg" width="100%">
</picture>

* **Java Full-Stack Systems:** Deepening mastery of Java 21 features (virtual threads, pattern matching, records) and Spring Boot application architecture.
* **Data Structures &amp; Algorithmic Analysis:** Exploring graph algorithms, dynamic programming, and computational complexity for real-world backend applications.
* **Database Schema Design &amp; Index Optimization:** Investigating B-tree indexing strategies, query execution plans, and transaction isolation levels in relational databases.
* **Production-Minded Software Engineering:** Building reliable, modular software systems with deterministic error boundaries, comprehensive test coverage, and clean documentation.

---

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/section-stats.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/section-stats-light.svg">
  <img alt="Activity &amp; Metrics" src="assets/section-stats.svg" width="100%">
</picture>

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats-anuraghazra1.vercel.app/api?username=sars-23&show_icons=true&bg_color=0D1117&title_color=F59E0B&icon_color=38BDF8&text_color=94A3B8&border_color=30363D">
    <source media="(prefers-color-scheme: light)" srcset="https://github-readme-stats-anuraghazra1.vercel.app/api?username=sars-23&show_icons=true&bg_color=F8FAFC&title_color=D97706&icon_color=0284C7&text_color=475569&border_color=E2E8F0">
    <img src="https://github-readme-stats-anuraghazra1.vercel.app/api?username=sars-23&show_icons=true&bg_color=0D1117&title_color=F59E0B&icon_color=38BDF8&text_color=94A3B8&border_color=30363D" alt="Saransh's GitHub Stats" />
  </picture>
  &nbsp;&nbsp;
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats-anuraghazra1.vercel.app/api/top-langs/?username=sars-23&layout=compact&bg_color=0D1117&title_color=F59E0B&text_color=94A3B8&border_color=30363D">
    <source media="(prefers-color-scheme: light)" srcset="https://github-readme-stats-anuraghazra1.vercel.app/api/top-langs/?username=sars-23&layout=compact&bg_color=F8FAFC&title_color=D97706&text_color=475569&border_color=E2E8F0">
    <img src="https://github-readme-stats-anuraghazra1.vercel.app/api/top-langs/?username=sars-23&layout=compact&bg_color=0D1117&title_color=F59E0B&text_color=94A3B8&border_color=30363D" alt="Top Languages" />
  </picture>
</div>

<br>

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com?user=sars-23&theme=dark&background=0D1117&border=30363D&stroke=F59E0B&ring=F59E0B&fire=F59E0B&currStreakLabel=F59E0B&sideLabels=94A3B8&dates=64748B">
    <source media="(prefers-color-scheme: light)" srcset="https://streak-stats.demolab.com?user=sars-23&background=F8FAFC&border=E2E8F0&stroke=D97706&ring=D97706&fire=D97706&currStreakLabel=D97706&currStreakNum=0F172A&sideLabels=475569&sideNums=0F172A&dates=64748B">
    <img src="https://streak-stats.demolab.com?user=sars-23&theme=dark&background=0D1117&border=30363D&stroke=F59E0B&ring=F59E0B&fire=F59E0B&currStreakLabel=F59E0B&sideLabels=94A3B8&dates=64748B" alt="GitHub Contribution Streak" />
  </picture>
</div>

---

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/section-contact.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/section-contact-light.svg">
  <img alt="Contact &amp; Links" src="assets/section-contact.svg" width="100%">
</picture>

<p align="center">
  <a href="https://github.com/sars-23">
    <img src="https://img.shields.io/badge/GitHub-@sars--23-181717?style=for-the-badge&logo=github&logoColor=white&labelColor=0d1117" alt="GitHub">
  </a>
  &nbsp;
  <a href="https://sars-23.github.io/Portfolio/">
    <img src="https://img.shields.io/badge/Portfolio-sars--23.github.io%2FPortfolio-f59e0b?style=for-the-badge&logo=googlechrome&logoColor=white&labelColor=0d1117" alt="Portfolio">
  </a>
  &nbsp;
  <a href="mailto:saransh.9822@gmail.com">
    <img src="https://img.shields.io/badge/Email-saransh.9822@gmail.com-ea4335?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0d1117" alt="Email">
  </a>
</p>

<p align="center">
  <sub>B.Tech Computer Science Engineering • JECRC University (2023–2027) • Jaipur, Rajasthan, India</sub>
</p>

<br>

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/footer.svg">
    <source media="(prefers-color-scheme: light)" srcset="assets/footer-light.svg">
    <img alt="Profile Footer" src="assets/footer.svg" width="100%">
  </picture>
</div>
