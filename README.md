# word-counter3
from collections import Counter

def count_words(text: str) -> dict:
    # Make everything lowercase
    text = text.lower()
    
    # Replace common punctuation with spaces
    for ch in [".", ",", "!", "?", ":", ";", "(", ")", "\"", "'"]:
        text = text.replace(ch, " ")
    
    # Split into words
    words = text.split()
    
    # Count words
    return Counter(words)

if __name__ == "__main__":
    user_text = input("Enter text: ")
    counts = count_words(user_text)
    
    print("\nWord counts:")
    for word, count in counts.items():
        print(f"{word}: {count}")
