<img width="1916" height="544" alt="image" src="https://github.com/user-attachments/assets/e5fd90d4-ad85-4368-a36d-21218c6f742f" />

# مقدمة
في حال كنت تستخدم مدير الحزم `uv` استخدم الأمر التالي لتشغيل اللعبة 
`uv run`

و إلا يجب قبل تشغيل اللعبة استخدام الأمر التالي : 
`pip install neat-python pygame`

# بدء التدريب

في حال كنت تريد بدء التدريب فقط استخدم الأمر `python main.py`

# اختبار أفضل نسخة

في حال كنت تريد اختبار أفضل نسخة استخدم الأمر `python test.py`

# تجربة اللعبة يدويًا

أذهب إلى ملف `main.py` و ألصق التالي بعد `if __name__ == '__main__':` :

```
if __name__ == '__main__':
    #أقرا readme.md
    local_dir = os.path.dirname(__file__) if '__file__' in globals() else os.getcwd()
    config_path = os.path.join(local_dir, 'config.txt')

    SAVE_DIR = os.path.join(local_dir, 'dino_saves')
    OLD_DIR = os.path.join(local_dir, 'old_saves')


    #run(config_path)
     Game_loop(pygame.time.Clock(),is_AI=False)
```

# تمثيل التدريب

في حال كنت تريد تمثيل التدريب الأخير اذهب إلى `graph.py` و ألصق التالي بعد `if __name__ == "__main__":` :

```python

if __name__ == "__main__":

plot_best_fitness_per_generation()

```

في حال تمثيل كل التدريبات السابقة أنسخ ألصق التالي :

```

if __name__ == "__main__":

for dic in os.listdir(OLD_DIR):

if os.path.isdir(os.path.join(OLD_DIR, dic)):

print(f"Processing directory: {dic}")

plot_best_fitness_per_generation(os.path.join(OLD_DIR, dic))

```



# أساس المشروع 
أساس المشروع مأخوذ من [UPocek](https://github.com/UPocek/Dinosaur_Game_AI/tree/main)


# Introduction

If you are using the **uv** package manager, run the following command to start the game:

```
uv run
```

Otherwise, before running the game, you must install the required dependencies using:

```
pip install neat-python pygame
```

---

## Starting Training

If you want to start training, simply run:

```
python main.py
```

---

## Testing the Best Model

If you want to test the best saved version, use:

```
python test.py
```

---

## Playing the Game Manually

Go to the `main.py` file and paste the following code after
`if __name__ == '__main__':`

```python
if __name__ == '__main__':
    # Read readme.md
    local_dir = os.path.dirname(__file__) if '__file__' in globals() else os.getcwd()
    config_path = os.path.join(local_dir, 'config.txt')

    SAVE_DIR = os.path.join(local_dir, 'dino_saves')
    OLD_DIR = os.path.join(local_dir, 'old_saves')

    #run(config_path)
    Game_loop(pygame.time.Clock(), is_AI=False)
```

---

## Visualizing Training

If you want to visualize the **most recent training**, go to `graph.py` and paste the following code after
`if __name__ == "__main__":`

```python
if __name__ == "__main__":
    plot_best_fitness_per_generation()
```

If you want to visualize **all previous training sessions**, paste the following code instead:

```python
if __name__ == "__main__":
    for dic in os.listdir(OLD_DIR):
        if os.path.isdir(os.path.join(OLD_DIR, dic)):
            print(f"Processing directory: {dic}")
            plot_best_fitness_per_generation(os.path.join(OLD_DIR, dic))
```

---

## Project Basis

The base of this project was adapted from [UPocek](https://github.com/UPocek/Dinosaur_Game_AI/tree/main)
