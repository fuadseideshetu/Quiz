# Quiz
This is a question of six subjects (maths,chemistry, physics, English, biology, aptitude) and there answers.
# Quations
---
Subject Questions and Answers Generator

Here's a complete Python program that generates questions with answers for English, Math, Physics, Chemistry, Biology, and SAT:

```python
import random

class QuestionGenerator:
    def __init__(self):
        self.questions = {
            "English": self.get_english_questions(),
            "Maths": self.get_maths_questions(),
            "Physics": self.get_physics_questions(),
            "Chemistry": self.get_chemistry_questions(),
            "Biology": self.get_biology_questions(),
            "SAT": self.get_sat_questions()
        }
    
    def get_english_questions(self):
        return [
            {
                "question": "Identify the grammatical error: 'Neither of the boys are coming to the party.'",
                "answer": "The error is subject-verb agreement. 'Neither' is singular and should take 'is' not 'are'."
            },
            {
                "question": "Which word is a synonym for 'ubiquitous'? a) rare b) scarce c) omnipresent d) limited",
                "answer": "c) omnipresent"
            },
            {
                "question": "Rewrite in passive voice: 'The committee will announce the results tomorrow.'",
                "answer": "The results will be announced by the committee tomorrow."
            },
            {
                "question": "What literary device is used in: 'The stars danced playfully in the moonlit sky'?",
                "answer": "Personification (giving human qualities to stars)"
            },
            {
                "question": "What is the past participle of the verb 'to swim'?",
                "answer": "swum"
            }
        ]
    
    def get_maths_questions(self):
        return [
            {
                "question": "Solve for x: 3x + 7 = 22",
                "answer": "x = 5"
            },
            {
                "question": "Calculate the area of a circle with radius 5 cm.",
                "answer": "78.54 cm² (using πr² with π=3.1416)"
            },
            {
                "question": "Simplify: (2x² + 3x - 5) + (4x² - 2x + 7)",
                "answer": "6x² + x + 2"
            },
            {
                "question": "Find y when x=3 in the equation y = 2x² - 4x + 1",
                "answer": "y = 7"
            }
        ]
    
    def get_physics_questions(self):
        return [
            {
                "question": "Calculate the force required to accelerate a 5 kg object at 3 m/s².",
                "answer": "15 N (using F = m × a)"
            },
            {
                "question": "Explain the difference between kinetic and potential energy.",
                "answer": "Kinetic energy is energy of motion, while potential energy is stored energy based on position or state."
            },
            {
                "question": "A car travels 150 km in 2 hours. What is its average speed in m/s?",
                "answer": "20.83 m/s (150 km = 150,000 m, 2 hours = 7200 s, speed = distance/time)"
            },
            {
                "question": "Describe Newton's Third Law of Motion.",
                "answer": "For every action, there is an equal and opposite reaction."
            }
        ]
    
    def get_chemistry_questions(self):
        return [
            {
                "question": "Balance the equation: H₂ + O₂ → H₂O",
                "answer": "2H₂ + O₂ → 2H₂O"
            },
            {
                "question": "What is the difference between an element and a compound?",
                "answer": "An element is a pure substance made of one type of atom. A compound is made of two or more elements chemically combined."
            },
            {
                "question": "How many moles are in 25 grams of water (H₂O)?",
                "answer": "Approximately 1.39 moles (molar mass of H₂O is 18 g/mol)"
            },
            {
                "question": "Explain the process of electrolysis.",
                "answer": "Electrolysis is a process that uses electrical energy to drive a non-spontaneous chemical reaction."
            }
        ]
    
    def get_biology_questions(self):
        return [
            {
                "question": "Describe the process of photosynthesis.",
                "answer": "Photosynthesis is the process where plants convert light energy, water, and CO₂ into glucose and oxygen."
            },
            {
                "question": "What is the difference between mitosis and meiosis?",
                "answer": "Mitosis produces two identical diploid cells for growth and repair. Meiosis produces four genetically different haploid cells for reproduction."
            },
            {
                "question": "Explain how enzymes function as biological catalysts.",
                "answer": "Enzymes speed up chemical reactions by lowering the activation energy without being consumed in the process."
            },
            {
                "question": "Describe the structure of DNA.",
                "answer": "DNA is a double helix structure made of nucleotides containing a sugar-phosphate backbone and nitrogenous bases (A,T,C,G)."
            }
        ]
    
    def get_sat_questions(self):
        return [
            {
                "question": "If 3x - 7 = 17, what is the value of x?",
                "answer": "x = 8"
            },
            {
                "question": "In the equation y = 3x² - 2x + 5, what is y when x = -2?",
                "answer": "y = 21"
            },
            {
                "question": "The ratio of boys to girls is 3:5. If there are 24 students total, how many boys are there?",
                "answer": "9 boys (3/8 of 24)"
            },
            {
                "question": "A rectangle has length twice its width. If perimeter is 36 cm, what is the area?",
                "answer": "72 cm² (width=6cm, length=12cm)"
            }
        ]
    
    def display_questions(self, subject):
        if subject in self.questions:
            print(f"\n{subject} Questions:")
            print("=" * 50)
            for i, qa in enumerate(self.questions[subject], 1):
                print(f"{i}. {qa['question']}")
            
            show_answers = input("\nWould you like to see the answers? (yes/no): ").lower()
            if show_answers == 'yes':
                print(f"\n{subject} Answers:")
                print("=" * 50)
                for i, qa in enumerate(self.questions[subject], 1):
                    print(f"{i}. {qa['answer']}")
        else:
            print("Subject not found!")
    
    def display_all_questions(self):
        for subject in self.questions:
            self.display_questions(subject)
            input("\nPress Enter to continue to next subject...")
    
    def run(self):
        while True:
            print("\n" + "="*50)
            print("QUESTION GENERATOR")
            print("="*50)
            print("1. English (5 questions)")
            print("2. Maths (4 questions)")
            print("3. Physics (4 questions)")
            print("4. Chemistry (4 questions)")
            print("5. Biology (4 questions)")
            print("6. SAT (4 questions)")
            print("7. All subjects")
            print("8. Exit")
            
            choice = input("\nEnter your choice (1-8): ")
            
            if choice == '1':
                self.display_questions("English")
            elif choice == '2':
                self.display_questions("Maths")
            elif choice == '3':
                self.display_questions("Physics")
            elif choice == '4':
                self.display_questions("Chemistry")
            elif choice == '5':
                self.display_questions("Biology")
            elif choice == '6':
                self.display_questions("SAT")
            elif choice == '7':
                self.display_all_questions()
            elif choice == '8':
                print("Goodbye!")
                break
            else:
                print("Invalid choice! Please try again.")

# Run the program
if __name__ == "__main__":
    generator = QuestionGenerator()
    generator.run()
```

This program:

1. Creates a class QuestionGenerator that contains questions and answers for each subject
2. Provides 5 questions for English and 4 questions for each other subject
3. Includes a menu system to select which subject's questions to view
4. Gives the option to show answers after displaying questions
5. Allows viewing all subjects sequentially



```python
questions = {
    "English": [
        {
            "question": "Which of the following sentences is grammatically correct?",
            "options": ["A. She don't like apples.", "B. He doesn't likes apples.", "C. They doesn't like apples.", "D. He doesn't like apples."],
            "answer": "D"
        },
        {
            "question": "Choose the correct word: The team celebrated _____ victory.",
            "options": ["A. their", "B. its", "C. they're", "D. it's"],
            "answer": "B"
        },
        {
            "question": "Identify the sentence with proper parallel structure:",
            "options": ["A. She likes hiking, swimming, and to ride a bicycle.", "B. She likes to hike, swimming, and riding a bicycle.", "C. She likes hiking, swimming, and riding a bicycle.", "D. She likes to hike, to swim, and riding a bicycle."],
            "answer": "C"
        },
        {
            "question": "Which word is misspelled?",
            "options": ["A. necessary", "B. separate", "C. definately", "D. government"],
            "answer": "C"
        },
        {
            "question": "What is the literary term for giving human qualities to non-human things?",
            "options": ["A. Metaphor", "B. Simile", "C. Personification", "D. Hyperbole"],
            "answer": "C"
        }
    ],
    "Mathematics": [
        {
            "question": "Solve for x: 2x + 5 = 15",
            "options": ["A. 5", "B. 7.5", "C. 10", "D. 20"],
            "answer": "A"
        },
        {
            "question": "What is the area of a circle with radius 4?",
            "options": ["A. 8π", "B. 16π", "C. 32π", "D. 64π"],
            "answer": "B"
        },
        {
            "question": "Simplify: (3x²y³)²",
            "options": ["A. 6x⁴y⁶", "B. 9x⁴y⁵", "C. 9x⁴y⁶", "D. 6x⁴y⁵"],
            "answer": "C"
        },
        {
            "question": "If f(x) = 2x - 3, what is f(5)?",
            "options": ["A. 2", "B. 7", "C. 10", "D. 13"],
            "answer": "B"
        },
        {
            "question": "What is the slope of the line y = -2x + 7?",
            "options": ["A. 2", "B. -2", "C. 7", "D. -7"],
            "answer": "B"
        }
    ],
    "Chemistry": [
        {
            "question": "What is the atomic number of oxygen?",
            "options": ["A. 6", "B. 8", "C. 16", "D. 32"],
            "answer": "B"
        },
        {
            "question": "Which of these is a noble gas?",
            "options": ["A. Oxygen", "B. Nitrogen", "C. Helium", "D. Chlorine"],
            "answer": "C"
        },
        {
            "question": "What is the pH of a neutral solution?",
            "options": ["A. 0", "B. 7", "C. 14", "D. 1"],
            "answer": "B"
        },
        {
            "question": "How many electrons can the first energy level hold?",
            "options": ["A. 2", "B. 8", "C. 18", "D. 32"],
            "answer": "A"
        },
        {
            "question": "What type of bond involves the sharing of electrons?",
            "options": ["A. Ionic", "B. Covalent", "C. Metallic", "D. Hydrogen"],
            "answer": "B"
        }
    ],
    "Physics": [
        {
            "question": "What is the SI unit of force?",
            "options": ["A. Joule", "B. Watt", "C. Newton", "D. Pascal"],
            "answer": "C"
        },
        {
            "question": "Which law states that for every action, there is an equal and opposite reaction?",
            "options": ["A. Newton's First Law", "B. Newton's Second Law", "C. Newton's Third Law", "D. Law of Conservation of Energy"],
            "answer": "C"
        },
        {
            "question": "What is the acceleration due to gravity on Earth?",
            "options": ["A. 8.9 m/s²", "B. 9.8 m/s²", "C. 10 m/s²", "D. 11.2 m/s²"],
            "answer": "B"
        },
        {
            "question": "Which color of light has the longest wavelength?",
            "options": ["A. Violet", "B. Blue", "C. Green", "D. Red"],
            "answer": "D"
        },
        {
            "question": "What is the unit of electrical resistance?",
            "options": ["A. Volt", "B. Ampere", "C. Ohm", "D. Watt"],
            "answer": "C"
        }
    ],
    "Biology": [
        {
            "question": "What is the powerhouse of the cell?",
            "options": ["A. Nucleus", "B. Mitochondria", "C. Ribosome", "D. Golgi apparatus"],
            "answer": "B"
        },
        {
            "question": "Which process do plants use to make food?",
            "options": ["A. Respiration", "B. Photosynthesis", "C. Digestion", "D. Fermentation"],
            "answer": "B"
        },
        {
            "question": "How many chromosomes do humans have?",
            "options": ["A. 23", "B. 46", "C. 48", "D. 52"],
            "answer": "B"
        },
        {
            "question": "What is the basic unit of heredity?",
            "options": ["A. Cell", "B. Chromosome", "C. Gene", "D. Protein"],
            "answer": "C"
        },
        {
            "question": "Which blood type is known as the universal donor?",
            "options": ["A. A+", "B. B-", "C. AB+", "D. O-"],
            "answer": "D"
        }
    ],
    "SAT": [
        {
            "question": "If 3x + 2y = 12 and x - y = 1, what is the value of x?",
            "options": ["A. 2", "B. 2.8", "C. 3", "D. 3.2"],
            "answer": "B"
        },
        {
            "question": "The word 'ubiquitous' most nearly means:",
            "options": ["A. rare", "B. everywhere", "C. complicated", "D. ancient"],
            "answer": "B"
        },
        {
            "question": "In the equation y = kx, if y = 15 when x = 3, what is y when x = 7?",
            "options": ["A. 21", "B. 28", "C. 35", "D. 42"],
            "answer": "C"
        },
        {
            "question": "Which sentence demonstrates correct punctuation?",
            "options": ["A. The students, who studied hard, passed the exam.", "B. The students who studied hard, passed the exam.", "C. The students, who studied hard passed the exam.", "D. The students who studied hard passed the exam."],
            "answer": "A"
        },
        {
            "question": "If a² + b² = 25 and ab = 12, what is (a + b)²?",
            "options": ["A. 13", "B. 37", "C. 49", "D. 61"],
            "answer": "C"
        }
    ]
#Fuad Seid
"Mathematics": [
        {"question": "Solve for x: 2x + 3 = 13", "options": ["A) 4", "B) 6", "C) 7", "D) 5"], "answer": "A"},
        {"question": "The roots of x² - 5x + 6 = 0 are:", "options": ["A) 1 and 6", "B) 2 and 3", "C) 3 and 5", "D) 6 and 2"], "answer": "B"},
        {"question": "A train travels 120 km in 3 hours. Its average speed is:", "options": ["A) 30 km/h", "B) 60 km/h", "C) 40 km/h", "D) 80 km/h"], "answer": "B"},
        {"question": "If the perimeter of a square is 48 cm, the area is:", "options": ["A) 144 cm²", "B) 196 cm²", "C) 121 cm²", "D) 576 cm²"], "answer": "A"},
        {"question": "Simplify: (25 ÷ 5) + (12 ÷ 3)", "options": ["A) 3", "B) 7", "C) 9", "D) 11"], "answer": "D"}
    ],
    "Chemistry": [
        {"question": "Electronic configuration of Sodium (Z = 11):", "options": ["A) 2, 8, 1", "B) 2, 6, 3", "C) 2, 7, 2", "D) 2, 8, 2"], "answer": "A"},
        {"question": "Valency of Oxygen is:", "options": ["A) 1", "B) 2", "C) 3", "D) 4"], "answer": "B"},
        {"question": "Which of the following is a physical change?", "options": ["A) Burning of paper", "B) Melting of ice", "C) Rusting of iron", "D) Cooking rice"], "answer": "B"},
        {"question": "Law of Conservation of Mass states:", "options": ["A) Mass is lost", "B) Mass is gained", "C) Mass is neither created nor destroyed", "D) Mass changes"], "answer": "C"},
        {"question": "Ionic bond is formed by:", "options": ["A) Sharing of electrons", "B) Transfer of electrons", "C) Both A and B", "D) None"], "answer": "B"}
    ],
    "Biology": [
        {"question": "Function of mitochondria:", "options": ["A) Photosynthesis", "B) Protein synthesis", "C) Energy production", "D) Transport"], "answer": "C"},
        {"question": "Xylem transports:", "options": ["A) Food", "B) Water", "C) Oxygen", "D) Hormones"], "answer": "B"},
        {"question": "Photosynthesis produces:", "options": ["A) Oxygen and Glucose", "B) CO2 and Water", "C) Heat and ATP", "D) Protein and Oxygen"], "answer": "A"},
        {"question": "Aerobic respiration requires:", "options": ["A) Oxygen", "B) Nitrogen", "C) No oxygen", "D) Water only"], "answer": "A"},
        {"question": "Oxygen in humans is transported by:", "options": ["A) Platelets", "B) RBC", "C) WBC", "D) Plasma"], "answer": "B"}
    ],
    "English": [
        {"question": "Synonym of 'brave':", "options": ["A) Cowardly", "B) Courageous", "C) Weak", "D) Lazy"], "answer": "B"},
        {"question": "Passive voice of 'The teacher is explaining the lesson':", "options": ["A) The lesson was explained", "B) The lesson is being explained", "C) The teacher explains", "D) The lesson has been explained"], "answer": "B"},
        {"question": "Figure of speech in 'The sun smiled at us':", "options": ["A) Metaphor", "B) Simile", "C) Personification", "D) Hyperbole"], "answer": "C"},
        {"question": "Importance of reading:", "options": ["A) Makes us lazy", "B) Improves knowledge", "C) Wastes time", "D) Is boring"], "answer": "B"},
        {"question": "Correct sentence: She is taller ___ her brother.", "options": ["A) than", "B) then", "C) there", "D) that"], "answer": "A"}
    ],
    "Physics": [
        {"question": "Newton’s First Law is also called:", "options": ["A) Law of Acceleration", "B) Law of Inertia", "C) Law of Gravity", "D) Law of Work"], "answer": "B"},
        {"question": "A car moves with velocity 20 m/s for 10 s. Distance covered =", "options": ["A) 100 m", "B) 150 m", "C) 200 m", "D) 250 m"], "answer": "C"},
        {"question": "SI unit of work is:", "options": ["A) Watt", "B) Joule", "C) Newton", "D) Pascal"], "answer": "B"},
        {"question": "Difference between mass and weight:", "options": ["A) Mass depends on gravity", "B) Weight depends on gravity", "C) Both depend on gravity", "D) Neither"], "answer": "B"},
        {"question": "Splitting of white light by prism is called:", "options": ["A) Reflection", "B) Refraction", "C) Dispersion", "D) Diffraction"], "answer": "C"}
    ],
    "Aptitude": [
        {"question": "If 5 pens cost $75, cost of 8 pens =", "options": ["A) $100", "B) $110", "C) $120", "D) $150"], "answer": "C"},
        {"question": "Average of 4 numbers = 20. Sum =", "options": ["A) 60", "B) 70", "C) 80", "D) 90"], "answer": "C"},
        {"question": "Next term: 2, 4, 8, 16, ?", "options": ["A) 18", "B) 24", "C) 30", "D) 32"], "answer": "D"},
        {"question": "A man walks 3 km east, then 4 km north. Distance from start =", "options": ["A) 5 km", "B) 6 km", "C) 7 km", "D) 8 km"], "answer": "A"},
        {"question": "Boys : Girls = 3 : 2. If 30 students, girls =", "options": ["A) 10", "B) 12", "C) 15", "D) 18"], "answer": "C"}
    ]
}

total_score = 0
total_questions = 0

for subject, questions in quizzes.items():
    print(f"\n--- {subject} ---")
    for q in questions:
        print("\n" + q["question"])
        for option in q["options"]:
            print(option)
        user_ans = input("Your answer (A/B/C/D): ")
        total_questions += 1
        if user_ans.upper() == q["answer"]:
            print("✅ Correct!")
            total_score += 1
        else:
            print(f"❌ Wrong! Correct answer is {q['answer']}")

print(f"\nYour Total Score = {total_score}/{total_questions}")
fuad

