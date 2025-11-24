## Question List (with Trait Mapping)

For each statement, user answers from 1–5 as per the scale.

### Openness (O)

O1. *I enjoy exploring new ideas, topics, or concepts, even if they are unrelated to my field.*  
O2. *I like trying out new ways of doing things instead of always sticking to the usual methods.*  
O3. *I am curious about how things work and often research topics just out of interest.*  
O4. *I enjoy creative activities such as writing, designing, drawing, or brainstorming new concepts.*  
O5 (R). *I prefer predictable tasks over anything that requires creativity or imagination.*

### Conscientiousness (C)

C1. *I usually finish tasks before the deadline, even if no one is checking on me.*  
C2. *I like planning my day or week and following a schedule.*  
C3. *People can rely on me to keep my commitments and promises.*  
C4. *I pay attention to details and try to avoid careless mistakes.*  
C5 (R). *I often leave work or assignments unfinished and tell myself I will do them “later”.*

### Extraversion (E)

E1. *I feel energized when I am around people, discussing ideas or working in teams.*  
E2. *I am comfortable initiating conversations with new people (in college, events, or online).*  
E3. *I enjoy being in roles where I have to present, pitch, or speak in front of others.*  
E4. *I prefer collaborative work over working completely alone.*  
E5 (R). *I avoid group activities whenever possible and prefer to stay in the background.*

### Agreeableness (A)

A1. *I try to understand other people’s perspectives, even when I disagree with them.*  
A2. *I am willing to help classmates/colleagues with their work when they are struggling.*  
A3. *I try to maintain harmony in a group and avoid unnecessary conflicts.*  
A4. *People would describe me as cooperative and easy to work with.*  
A5 (R). *I don’t really care how my decisions affect others, as long as I get my work done.*

### Neuroticism (N)

N1. *I often feel stressed or anxious when there is uncertainty about my future or career.*  
N2. *I tend to overthink small mistakes or negative feedback for a long time.*  
N3. *When deadlines or exams are near, I find it hard to stay calm.*  
N4 (R). *I stay emotionally steady even during difficult situations or pressure.*  
N5. *My mood gets affected easily by what others say or think about me.*

How to Score (for later backend logic)

Add this to the doc so future you knows how to implement:

## Scoring Logic (For Backend)

Each response is on a scale of 1–5.

For NON-reverse questions:
- Use score as is (1 to 5).

For REVERSE-scored questions (marked with R):
- Convert using: `score_reversed = 6 - original_score`
  - So:
    - 1 → 5
    - 2 → 4
    - 3 → 3
    - 4 → 2
    - 5 → 1

Trait score calculation:
- For each trait (O, C, E, A, N):
  - Take the average of all its (processed) question scores.
  - Example:
    - Openness = (O1 + O2 + O3 + O4 + O5_processed) / 5

Normalization (optional for ML):
- Keep traits as 1–5
  OR
- Normalize to 0–1 range using: `(avg_score - 1) / 4`
