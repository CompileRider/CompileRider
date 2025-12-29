<div align="center">

# 👋 Hi there! I'm Esmil

### Python Developer 🐍 | Always Learning 🚀 | Code + Coffee = ❤️

[![Profile Views](https://komarev.com/ghpvc/?username=CompileRIder&color=blueviolet&style=for-the-badge)](https://github.com/CompileRIder)

</div>

---

## 🐍 About Me

```python
class Developer:
    def __init__(self):
        self.name = "Esmil"
        self.languages = ["Python (my passion)", "C++ (foundation)"]
        self.currently_learning = "NLP & Machine Learning with Python"
        self.goal = "Building intelligent systems that understand human language"
        self.fun_fact = "Switched from C++ to Python specifically for NLP 🤖"
    
    def get_info(self):
        return {
            "name": self.name,
            "languages": self.languages,
            "learning": self.currently_learning,
            "status": "Always coding, always learning"
        }

# Creating instance
me = Developer()
print(f"Hi! I'm {me.name} 👋")
```

<img align="right" alt="Coding" width="400" src="https://raw.githubusercontent.com/abhisheknaiidu/abhisheknaiidu/master/code.gif">

- 🐍 **Languages:** Proficient in Python (focused on NLP), solid foundation in C++
- 🌱 **Currently Learning:** Natural Language Processing, Machine Learning fundamentals, and Neural Networks
- 🔧 **Working On:** NLP projects using NLTK and spaCy, text preprocessing pipelines
- 💬 **Ask me about:** Why I chose Python for NLP, text processing techniques, or my learning journey
- ⚡ **Fun fact:** Made the strategic switch from C++ to Python to dive into NLP and ML
- 🎯 **Goal:** Build systems that understand and generate human language

<br clear="right"/>

---

## 🛠️ What I Actually Know

<div align="center">

### Languages
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)

### NLP & ML Libraries
![NLTK](https://img.shields.io/badge/NLTK-154f3c?style=for-the-badge&logo=python&logoColor=white)
![spaCy](https://img.shields.io/badge/spaCy-09A3D5?style=for-the-badge&logo=spacy&logoColor=white)
![Scikit--learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)

### Data Science Tools
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

### Development Tools
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![VS Code](https://img.shields.io/badge/VS_Code-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![Pip](https://img.shields.io/badge/Pip-3776AB?style=for-the-badge&logo=pypi&logoColor=white)

</div>

---

## 📊 GitHub Stats

<div align="center">

<a href="https://github.com/CompileRIder">
  <img height="180em" src="https://github-readme-stats.vercel.app/api?username=CompileRIder&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true&hide_border=true&cache_seconds=86400"/>
  <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=CompileRIder&layout=compact&langs_count=8&theme=tokyonight&hide_border=true&cache_seconds=86400"/>
</a>

<a href="https://github.com/CompileRIder">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=CompileRIder&theme=tokyonight&hide_border=true" alt="CompileRIder's streak"/>
</a>

</div>

---

## 🏆 GitHub Trophies

<div align="center">

![Trophies](https://github-profile-trophy.vercel.app/?username=CompileRIder&theme=radical&no-frame=true&no-bg=true&column=7&margin-w=15&margin-h=15)

</div>

---

## 🚀 What I'm Working On

<table>
<tr>
<td width="50%">

### 💻 Current Focus
- Building automation scripts with Python
- Creating data analysis tools with Pandas and NumPy
- Developing personal projects to strengthen my Python skills
- Exploring web scraping and API integration

</td>
<td width="50%">

### 📚 Learning Path
- Advanced Python (decorators, generators, context managers)
- Data Science fundamentals
- Web development with Python frameworks
- Algorithm optimization and clean code practices

</td>
</tr>
</table>

---

## ⚡ The Reality of Coding

<div align="center">

```python
# My actual daily routine as a developer
import time
from typing import Optional

class DeveloperLife:
    """Represents the daily life of a Python developer"""
    
    def __init__(self):
        self.name = "Esmil"
        self.bugs_fixed = 0
        self.coffee_consumed = 0  # Starts at zero, increments throughout the day
        self.stackoverflow_visits = 0
    
    def drink_coffee(self) -> None:
        """Essential method for productivity"""
        self.coffee_consumed += 1
        print(f"☕ Coffee #{self.coffee_consumed} consumed. Energy restored!")
    
    def write_code(self) -> None:
        """Write beautiful Python code"""
        print("✍️  Writing code...")
        time.sleep(1)
    
    def test_code(self) -> bool:
        """Test if code actually works"""
        print("🧪 Testing code...")
        # In reality, it fails more often than we'd like
        return False  # Let's be honest
    
    def debug_code(self) -> None:
        """The art of finding that one missing comma"""
        print("🐛 Debugging...")
        self.stackoverflow_visits += 1
        self.drink_coffee()
    
    def daily_routine(self) -> None:
        """What every coding session looks like"""
        attempts = 0
        max_attempts = 5
        
        while attempts < max_attempts:
            try:
                self.write_code()
                
                if self.test_code():
                    print("✅ It works! Shipping to production! 🎉")
                    self.bugs_fixed += 1
                    break
                else:
                    raise Exception("Tests failed. Classic.")
                    
            except Exception as e:
                attempts += 1
                print(f"❌ Error: {e}")
                self.debug_code()
                print(f"🔄 Attempt {attempts}/{max_attempts}")
        
        if attempts == max_attempts:
            print("😅 Taking a break. Will fix it tomorrow.")
    
    def get_stats(self) -> dict:
        """Get current developer statistics"""
        return {
            "bugs_fixed": self.bugs_fixed,
            "coffee_consumed": self.coffee_consumed,
            "stackoverflow_visits": self.stackoverflow_visits
        }

# Starting my day
dev_life = DeveloperLife()
dev_life.daily_routine()
print(f"\n📊 Today's stats: {dev_life.get_stats()}")
```

</div>

### 🎯 Real Developer Facts

- 🐛 **My debugging process:** Print statements everywhere, Google the error, find a Stack Overflow answer from 2012 that somehow still works
- 🐍 **Why Python:** Started with C++ pointers and memory management. Python's simplicity was a revelation
- 💡 **Learning style:** Break things, fix them, break them again, finally understand how they work
- ☕ **Coffee equation:** `code_quality = base_skill * (coffee_consumed^0.5)` (diminishing returns after cup 3)
- 📚 **Documentation:** I read it... after the third error
- 🎮 **Debug breaks:** Sometimes the best solution comes after a gaming session
- 🔥 **Error messages:** My best teachers, though they could be more polite

---

## 🤝 Connect With Me

<div align="center">

[![GitHub](https://img.shields.io/badge/GitHub-CompileRIder-181717?style=for-the-badge&logo=github)](https://github.com/CompileRIder)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Esmil_Vicioso-0077B5?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/esmil-mercado-7885b9388/)
[![Email](https://img.shields.io/badge/Email-esmilviciosomercado-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:esmilviciosomercado@gmail.com)

</div>

---

<div align="center">

### 💼 Open to Collaborate

I'm interested in Python projects, especially those involving:
- Data analysis and visualization
- Automation and scripting solutions
- Learning opportunities in new Python frameworks
- Open source contributions

Also open to junior developer opportunities where I can grow and contribute!

[![Wave Footer](https://capsule-render.vercel.app/api?type=waving&color=0:4ec9b0,100:ff6b6b&height=120&section=footer)](https://github.com/CompileRIder)

**"Beautiful is better than ugly. Explicit is better than implicit."** - The Zen of Python 🐍

![Python](https://img.shields.io/badge/Made%20with-Python-3776AB?style=flat&logo=python&logoColor=white)
![Love](https://img.shields.io/badge/Made%20with-❤️%20%26%20Coffee-red?style=flat)
![Learning](https://img.shields.io/badge/Status-Always%20Learning-brightgreen?style=flat)

</div>
