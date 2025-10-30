# Exno.7-Develop a prompt-based application tailored to their personal needs, fostering creativity and practical problem-solving skills while leveraging the capabilities of large language models.

# Date:30.10.2025
# Register no.212223020008
# Aim: To develop a prompt-based application using ChatGPT - To demonstrate how to create a prompt-based application to organize daily tasks, showing the progression from simple to more advanced prompt designs and their corresponding outputs.

# AI Tools Required: 

1.Chat GPT

# Explanation: 
Prompt:
"Design a personal productivity assistant that can help manage daily tasks, schedule reminders, suggest wellness tips, and answer general queries. The assistant should interact using natural language and be adaptable to the user’s changing preferences over time."
# Procedure:
1. Define the core requirements of a personal productivity assistant.
2. Identify and construct appropriate prompts for each task using an LLM (e.g., ChatGPT).
3. Simulate natural user interaction through a simple interface or command-line system.
4. Collect feedback or inputs from users and adapt responses accordingly.
5. (Optional) Integrate basic memory to simulate preference adaptation.
EXPECTED OUTPUT: - (attached the drive link)
Output (Example Response by LLM):
Personal Productivity Assistant Features:
1. Daily Task Manager:
o Accept tasks via natural language (e.g., "Remind me to call mom at 6 PM").
o Organize tasks by priority and deadline.
o Provide daily summaries and pending items.
2. Smart Scheduler:
o Schedule events and set reminders using contextual understanding.
o Notify user of overlapping appointments or free time slots.
3. Wellness Tips Generator:
o Suggest daily wellness advice (hydration, exercise, screen-time breaks).
o Adapt suggestions based on past user preferences and responses.

## Simple Prompt (Level 1)
Basic Task Management Prompt:
```
text
You are a personal productivity assistant. Help me organize my daily tasks.
User input: "I need to finish my project report, call the dentist, and buy groceries"
Please list these tasks with priorities.
```
 ### Output:
```
Task List for Today:
1. HIGH - Finish project report (deadline dependent)
2. MEDIUM - Call the dentist (schedule appointment)
3. LOW - Buy groceries (flexible timing)
```
## Intermediate Prompt (Level 2)
Task Management with Context:
```
text
You are an advanced personal productivity assistant with memory of user preferences. 
Today's date: October 30, 2025

User Profile:
- Work: Software developer (9 AM - 6 PM)
- Preferences: Morning workouts, health-conscious
- Deadlines: Project due Friday

User Input: "I have a team meeting at 2 PM, need to review code, and want to exercise"

Please:
1. Organize tasks by priority
2. Suggest optimal timing
3. Identify any scheduling conflicts
4. Recommend wellness breaks
```
### Output
```Optimized Daily Schedule:

MORNING (Before 9 AM)
- 7:00 AM - 7:30 AM: Morning Workout (Exercise - Your Preference)
- 7:30 AM - 8:00 AM: Breakfast & Preparation

WORK HOURS (9 AM - 6 PM)
- 9:00 AM - 2:00 PM: Code Review (HIGH - Project deadline: Friday)
- 2:00 PM - 3:00 PM: Team Meeting
- 3:00 PM - 6:00 PM: Continue Code Review
- Reminder: Take a 5-min screen break at 12:30 PM and 4:30 PM

WELLNESS TIP:
Drink 8 glasses of water throughout the day. Your schedule shows 7 hours of work - ensure proper hydration and posture breaks.

No Conflicts Detected ✓
```
## Advanced Prompt (Level 3)
Multi-feature Personality-Adaptive Prompt:
```
text
You are "TaskMaster AI," an advanced personal productivity assistant with adaptive learning capabilities.

SYSTEM CONFIGURATION:
- User Name: [Student Name]
- User Type: Student/Professional
- Learning Style: Visual/Analytical/Kinesthetic
- Daily Energy Pattern: Peak hours: 10 AM - 12 PM, 2 PM - 4 PM
- Health Goals: Exercise 4x/week, 8 hours sleep, healthy diet
- Work Context: Academic/Professional projects with deadlines
- Timezone: IST (Indian Standard Time)

INTERACTION PROTOCOL:
1. Parse user input for intent (task creation, scheduling, wellness, query)
2. Cross-reference with existing tasks and deadlines
3. Detect stress indicators and suggest breaks
4. Provide adaptive suggestions based on past interactions
5. Generate actionable recommendations with time stamps

CURRENT USER INPUT:
"I have 3 assignments due next week, haven't exercised in 5 days, feeling overwhelmed, and need to prepare for an exam"

Please provide:
- Priority-ordered task breakdown with deadlines
- Optimal weekly schedule integrating exercise
- Stress management recommendations
- Daily wellness checklist
- Exam preparation strategy with milestones
```
### Output:
```
text
ANALYSIS: Overwhelm Detected ⚠️
Recommendation: Break tasks into smaller milestones to reduce stress.

PRIORITIZED TASK BREAKDOWN:
1. CRITICAL (Due: Nov 3) - Assignment 1 (3 parts: Research, Draft, Review)
   └─ Sub-tasks with daily targets
2. HIGH (Due: Nov 4) - Assignment 2 & Exam Prep
3. MEDIUM (Due: Nov 5) - Assignment 3

WEEKLY WELLNESS INTEGRATION:
- Monday, Wednesday, Friday: 45-min workout (6-7 AM) - matches your peak morning energy
- Daily: 15-min meditation before study sessions (suggested 10 AM)
- Hydration: Reminder every 2 hours during study sessions

STRESS MANAGEMENT PROTOCOL:
- Pomodoro technique: 25 min focus + 5 min break
- After 3 cycles: 15-min wellness break (walk, hydration, stretching)
- Sleep priority: Target 8 hours - avoid late-night study before exam

DAILY CHECKLIST TEMPLATE:
☐ Morning Routine (30 min)
☐ Exercise (3/3 remaining this week)
☐ Assignment work - Part 1 (your peak hours)
☐ Assignment work - Part 2 (your peak hours)
☐ Exam prep - Active recall (2 hours)
☐ Wellness activities (meditation, hydration)
☐ Evening review & next-day planning (20 min)

EXAM PREP MILESTONE:
- Day 1-2: Content Review (broad overview)
- Day 3-4: Active Recall Practice (testing yourself)
- Day 5-6: Problem areas deep-dive
- Day 7: Final revision & mock exam
```
# Implementation Strategy
A. Command-Line Interface Simulation
Here's a Python-based implementation template:
```
python
class PersonalProductivityAssistant:
    def __init__(self, user_name, llm_api_key):
        self.user_name = user_name
        self.tasks = []
        self.preferences = {}
        self.interaction_history = []
    
    def add_task(self, task_description):
        """Accept natural language task input"""
        # Send to LLM for parsing and categorization
        parsed_task = self.llm_parse(task_description)
        self.tasks.append(parsed_task)
        return self.generate_response(parsed_task)
    
    def schedule_event(self, event_description):
        """Handle scheduling with conflict detection"""
        event = self.llm_parse(event_description)
        conflicts = self.detect_conflicts(event)
        if conflicts:
            return self.suggest_alternatives(event, conflicts)
        return self.confirm_schedule(event)
    
    def suggest_wellness(self):
        """Generate adaptive wellness tips"""
        # Analyze user history and suggest personalized tips
        return self.generate_wellness_recommendation()
    
    def llm_parse(self, user_input):
        """Send to ChatGPT for NLP processing"""
        # API call to ChatGPT with appropriate prompt
        pass
    
    def detect_conflicts(self, new_event):
        """Check for scheduling conflicts"""
        pass
    
    def generate_response(self, task):
        """Format and return AI-generated response"""
        pass
```
# B. User Interaction Loop
```
text
Welcome to Personal Productivity Assistant!

Commands:
  'add task' - Add a new task
  'view schedule' - See your schedule
  'wellness tips' - Get wellness advice
  'ask' - Ask a general question
  'quit' - Exit

You: add task
Assistant: What task would you like to add?
You: Finish my project report and send it by Friday
Assistant: [Generates organized response with priority, deadline, reminders]

You: view schedule
Assistant: [Displays optimized schedule with time allocations]

You: wellness tips
Assistant: [Provides personalized wellness recommendations based on schedule]
```
## Progression 
| Aspect      | Level 1 (Simple) | Level 2 (Intermediate)     | Level 3 (Advanced)                  |
| ----------- | ---------------- | -------------------------- | ----------------------------------- |
| Input       | "Add tasks"      | "Schedule with context"    | "Natural conversation with history" |
| Processing  | Basic parsing    | Context-aware organization | Adaptive learning & personalization |
| Output      | Flat task list   | Organized schedule         | Dynamic recommendations             |
| Features    | List tasks       | Add timing & priorities    | Memory, wellness, stress detection  |
| Interaction | Command-based    | Query-based                | Conversational & adaptive           |

# Result: 
The lab exercise resulted in the creation of a prototype concept for a personal assistant powered by large language models. Students were able to:
 Understand how to tailor LLM prompts to real-life applications.
 Foster creativity by designing features suited to their personal or academic lives.
 Learn prompt engineering techniques for optimal interaction with AI tools.
 Experience the versatility and utility of generative AI in solving everyday problems.
