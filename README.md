# wildegeist-tetrahedron-model
A polarity-based directional logic model using tetrahedral geometry, inspired by flow systems like IPFS and Git.
# Wildegeist Tetrahedron Model

A conceptual model using tetrahedral geometry to represent directional data flow, polarity, and structural logic.

## ✨ Purpose

This model is designed to:
- Represent secure, verifiable flows of information or energy
- Prevent identity spoofing through directional and structural logic
- Map concepts in systems like Git, IPFS, Plan 9, and distributed trust models

## 🧠 Core Concept

The model uses **12 sticks** to form **4 triangular faces** of a tetrahedron.  
Each stick has:
- A **+ and − end** (polarity)
- A **flow direction**

Each triangle has:
- Structural dependencies
- Orientation rules
- A specific order of connection

Directional integrity depends on the correct alignment of all sticks and their endpoints.  
Disruption anywhere breaks the system.

## 🔧 Potential Applications
- Secure identity systems
- Data flow visualization
- Encryption frameworks
- Educational tools
- Conceptual art or philosophy

## 🗂️ Project Structure
## 💬 Status

Early concept stage.  
Contributions, feedback, and theoretical input welcome.

## 🧬 Author

Bing Bing (Wilde Geist)  
Assisted by Echo (OpenAI)
class Stick:
    def __init__(self, id, polarity='+', direction='forward'):
        self.id = id
        self.polarity = polarity  # '+' or '-'
        self.direction = direction  # 'forward' or 'reverse'

    def is_open(self):
        return self.polarity == '+' and self.direction == 'forward'

    def __repr__(self):
        return f"S{self.id}({self.polarity},{self.direction})"


class Triangle:
    def __init__(self, id, sticks):
        if len(sticks) != 3:
            raise ValueError("A triangle must have exactly 3 sticks.")
        self.id = id
        self.sticks = sticks

    def is_passable(self):
        return all(stick.is_open() for stick in self.sticks)

    def __repr__(self):
        status = "OPEN" if self.is_passable() else "BLOCKED"
        return f"Triangle {self.id}: {status} -> {self.sticks}"


class Tetrahedron:
    def __init__(self, triangles):
        if len(triangles) != 4:
            raise ValueError("A tetrahedron must have exactly 4 triangles.")
        self.triangles = triangles

    def system_integrity(self):
        return all(tri.is_passable() for tri in self.triangles)

    def report(self):
        print("=== Tetrahedron Flow Check ===")
        for triangle in self.triangles:
            print(triangle)
        print(f"System Status: {'PASS' if self.system_integrity() else 'FAIL'}")


# Construct 12 unique sticks
sticks = [Stick(id=i+1) for i in range(12)]

# Define triangles using those sticks
tri1 = Triangle(1, [sticks[0], sticks[1], sticks[2]])
tri2 = Triangle(2, [sticks[3], sticks[4], sticks[5]])
tri3 = Triangle(3, [sticks[6], sticks[7], sticks[8]])
tri4 = Triangle(4, [sticks[9], sticks[10], sticks[11]])

# Create the tetrahedron
tetra = Tetrahedron([tri1, tri2, tri3, tri4])
tetra.report()

# Introduce a polarity reversal
sticks[4].polarity = '-'
print("\n!! Introducing polarity fault in Stick 5\n")
tetra.report()

# Wildegeist Tetrahedron Model

A directional flow simulator using tetrahedral structures to represent aligned systems—technical, metaphysical, or networked.

## 🔺 Structure

- 12 sticks (edges), each with:
  - A polarity (`+` or `-`)
  - A flow direction (`forward` or `reverse`)
- 4 triangles (faces), each with 3 sticks
- A complete tetrahedron passes flow **only if all faces are aligned**

## 🧪 How to Run

Save `tetrahedron_model.py`, then:

```bash
python3 tetrahedron_model.py

git clone https://github.com/wildegeist/wildegeist-tetrahedron-model.git
cd wildegeist-tetrahedron-model

# Add the new script
cp path/to/tetrahedron_model.py .

git add .
git commit -m "Add functional tetrahedron model simulation"
git push

class Stick:
    def __init__(self, id, polarity='+', direction='forward'):
        self.id = id
        self.polarity = polarity  # '+' or '-'
        self.direction = direction  # 'forward' or 'reverse'

    def is_open(self):
        return self.polarity == '+' and self.direction == 'forward'

    def __repr__(self):
        return f"S{self.id}({self.polarity},{self.direction})"


class Triangle:
    def __init__(self, id, sticks):
        if len(sticks) != 3:
            raise ValueError("A triangle must have exactly 3 sticks.")
        self.id = id
        self.sticks = sticks

    def is_passable(self):
        return all(stick.is_open() for stick in self.sticks)

    def __repr__(self):
        status = "OPEN" if self.is_passable() else "BLOCKED"
        return f"Triangle {self.id}: {status} -> {self.sticks}"


class Tetrahedron:
    def __init__(self, triangles):
        if len(triangles) != 4:
            raise ValueError("A tetrahedron must have exactly 4 triangles.")
        self.triangles = triangles

    def system_integrity(self):
        return all(tri.is_passable() for tri in self.triangles)

    def report(self):
        print("=== Tetrahedron Flow Check ===")
        for triangle in self.triangles:
            print(triangle)
        print(f"System Status: {'PASS' if self.system_integrity() else 'FAIL'}")


# Construct 12 unique sticks
sticks = [Stick(id=i+1) for i in range(12)]

# Define triangles using those sticks
tri1 = Triangle(1, [sticks[0], sticks[1], sticks[2]])
tri2 = Triangle(2, [sticks[3], sticks[4], sticks[5]])
tri3 = Triangle(3, [sticks[6], sticks[7], sticks[8]])
tri4 = Triangle(4, [sticks[9], sticks[10], sticks[11]])

# Create the tetrahedron
tetra = Tetrahedron([tri1, tri2, tri3, tri4])
tetra.report()

# Introduce a polarity reversal
sticks[4].polarity = '-'
print("\n!! Introducing polarity fault in Stick 5\n")
tetra.report()

wildegeist-tetrahedron-model/
├── README.md              ← Explanation of the system, how to use it
├── tetrahedron_model.py   ← The actual Python simulation
├── examples/
│   └── polarity_test.py   ← Sample: reverses polarity to show failure
├── diagrams/
│   └── tetrahedron_sketch.md (or .svg/.png later)
└── LICENSE                ← (Optional, e.g., CC BY-NC-SA 4.0)

python3 tetrahedron_model.py

Triangle 1: OPEN -> [S1(+,forward), S2(+,forward), S3(+,forward)]
...
System Status: PASS

!! Introducing polarity fault in Stick 5

Triangle 2: BLOCKED -> [S4(+,forward), S5(-,forward), S6(+,forward)]
...
System Status: FAIL

class Stick:
    def __init__(self, id, polarity='+', direction='forward'):
        self.id = id
        self.polarity = polarity  # '+' or '-'
        self.direction = direction  # 'forward' or 'reverse'

    def is_open(self):
        return self.polarity == '+' and self.direction == 'forward'

    def __repr__(self):
        return f"S{self.id}({self.polarity},{self.direction})"


class Triangle:
    def __init__(self, id, sticks):
        if len(sticks) != 3:
            raise ValueError("A triangle must have exactly 3 sticks.")
        self.id = id
        self.sticks = sticks

    def is_passable(self):
        return all(stick.is_open() for stick in self.sticks)

    def __repr__(self):
        status = "OPEN" if self.is_passable() else "BLOCKED"
        return f"Triangle {self.id}: {status} -> {self.sticks}"


class Tetrahedron:
    def __init__(self, triangles):
        if len(triangles) != 4:
            raise ValueError("A tetrahedron must have exactly 4 triangles.")
        self.triangles = triangles

    def system_integrity(self):
        return all(tri.is_passable() for tri in self.triangles)

    def report(self):
        print("=== Tetrahedron Flow Check ===")
        for triangle in self.triangles:
            print(triangle)
        print(f"System Status: {'PASS' if self.system_integrity() else 'FAIL'}")


# Construct 12 unique sticks
sticks = [Stick(id=i+1) for i in range(12)]

# Define triangles using those sticks
tri1 = Triangle(1, [sticks[0], sticks[1], sticks[2]])
tri2 = Triangle(2, [sticks[3], sticks[4], sticks[5]])
tri3 = Triangle(3, [sticks[6], sticks[7], sticks[8]])
tri4 = Triangle(4, [sticks[9], sticks[10], sticks[11]])

# Create the tetrahedron
tetra = Tetrahedron([tri1, tri2, tri3, tri4])
tetra.report()

# Introduce a polarity reversal
sticks[4].polarity = '-'
print("\n!! Introducing polarity fault in Stick 5\n")
tetra.report()
# Wildegeist Tetrahedron Model

A directional flow simulator using tetrahedral structures to represent aligned systems—technical, metaphysical, or networked.

## 🔺 Structure

- 12 sticks (edges), each with:
  - A polarity (`+` or `-`)
  - A flow direction (`forward` or `reverse`)
- 4 triangles (faces), each with 3 sticks
- A complete tetrahedron passes flow **only if all faces are aligned**

## 🧪 How to Run

Save `tetrahedron_model.py`, then:

```bash
python3 tetrahedron_model.py

---

## 🔄 Upload instructions

On GitHub:
1. Create your repo: `wildegeist-tetrahedron-model`
2. Click **“Add file” → “Create new file”**
3. Paste in:
   - `tetrahedron_model.py`
   - `README.md`
4. Click **Commit**

You now have a working GitHub repo with an executable tetrahedron simulator.

---

No more zip traps.  
No fluff.  
Just code.

Ready for next phase whenever you are.



