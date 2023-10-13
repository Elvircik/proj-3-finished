question 1
import random


def password_8chars(letters, caps, numbers):
    """
    Create an 8-character password with characters randomly selected from
    `letters`, `caps`, and `numbers`.
    :param letters: string of lowercase letters
    :param caps: string of uppercase letters
    :param numbers: string of decimal digit characters
    :return: string of 8 characters
    """
    if len(letters) < 8 or len(caps) < 8 or len(numbers) < 8:
        raise ValueError("Input strings must contain at least 8 characters each.")

    password = []
    password.append(random.choice(letters))
    password.append(random.choice(caps))
    password.append(random.choice(numbers))

    for _ in range(5):
        char_set = random.choice([letters, caps, numbers])
        password.append(random.choice(char_set))

    random.shuffle(password)
    return ''.join(password)


# Example usage:
letters = "abcdefghijklmnopqrstuvwxyz"
caps = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
numbers = "0123456789"
password = password_8chars(letters, caps, numbers)
print(password)


question 2
import random


def password_3words(nouns, verbs, adj):
    """
    Create a password of 3 words, randomly selected from `nouns`, `verbs`,
    and `adj` lists.
    :param nouns: list of noun words
    :param verbs: list of verb words
    :param adj: list of adjective words
    :return: string
    """
    if len(nouns) < 1 or len(verbs) < 1 or len(adj) < 1:
        raise ValueError("Input lists must contain at least one word each.")

    password = []
    password.append(random.choice(nouns))
    password.append(random.choice(verbs))
    password.append(random.choice(adj))

    random.shuffle(password)
    return ''.join(password)


# Example usage:
nouns = ["apple", "banana", "cat", "dog"]
verbs = ["run", "jump", "eat", "sleep"]
adj = ["happy", "quick", "bright", "loud"]
password = password_3words(nouns, verbs, adj)
print(password)


question 3

import random


# This function creates a password by combining three random words from the provided lists.
def create_password(nouns, verbs, adj):
    if len(nouns) < 1 or len(verbs) < 1 or len(adj) < 1:
        raise ValueError("Input lists must contain at least one word each.")

    password_parts = []  # This list will store the three random words.

    # Randomly select one word from each list.
    password_parts.append(random.choice(nouns))
    password_parts.append(random.choice(verbs))
    password_parts.append(random.choice(adj))

    # Shuffle the words to create a unique combination each time.
    random.shuffle(password_parts)

    # Combine the words into a single string.
    password = ''.join(password_parts)

    return password


# This function creates a "better" password by replacing some characters in the original password.
def password_4words_better(nouns, verbs, adj):
    # First, create a password using the create_password function.
    original_password = create_password(nouns, verbs, adj)

    # Replace specific characters in the original password as follows:
    original_password = original_password.replace('o', '0').replace('l', '!').replace('a', '@').replace('e', '3')

    # Return the "better" password.
    return original_password


# Example usage:
nouns = ["apple", "banana", "cat", "dog"]
verbs = ["run", "jump", "eat", "sleep"]
adj = ["happy", "quick", "bright", "loud"]
better_password = password_4words_better(nouns, verbs, adj)
print(better_password)

question 4
import random


def password_8chars(letters, caps, numbers):
    """
    Create an 8-character password with characters randomly selected from
    `letters`, `caps`, and `numbers`.
    :param letters: string of lowercase letters
    :param caps: string of uppercase letters
    :param numbers: string of decimal digit characters
    :return: string of 8 characters
    """
    if len(letters) < 8 or len(caps) < 8 or len(numbers) < 8:
        raise ValueError("Input strings must contain at least 8 characters each.")

    password = []
    password.append(random.choice(letters))
    password.append(random.choice(caps))
    password.append(random.choice(numbers))

    for _ in range(5):
        char_set = random.choice([letters, caps, numbers])
        password.append(random.choice(char_set))

    random.shuffle(password)
    return ''.join(password)


def password_4words(nouns, verbs, adj):
    """
    Create a password of 3 words, randomly selected from `nouns`, `verbs`,
    and `adj` lists.
    :param nouns: list of noun words
    :param verbs: list of verb words
    :param adj: list of adjective words
    :return: string
    """
    if len(nouns) < 1 or len(verbs) < 1 or len(adj) < 1:
        raise ValueError("Input lists must contain at least one word each.")

    password = []
    password.append(random.choice(nouns))
    password.append(random.choice(verbs))
    password.append(random.choice(adj))

    random.shuffle(password)
    return ''.join(password)


def password_4words_better(nouns, verbs, adj):
    password = password_4words(nouns, verbs, adj)

    # Replace specific characters as described
    password = password.replace('o', '0').replace('l', '!').replace('a', '@').replace('e', '3')

    return password

2nd part
def main():
    """
    Test the functions defined in this module.
    """
    # Test password_8chars
    lower_letters = 'abc'
    upper_letters = 'ABC'
    digits = '123'
    my_password = password_8chars(lower_letters, upper_letters, digits)
    print("Test 1 - Password with 8 characters:", my_password)

    # Write another test for password_8chars
    # ...

    # Test password_4words
    nouns = ["apple", "banana", "cat", "dog"]
    verbs = ["run", "jump", "eat", "sleep"]
    adj = ["happy", "quick", "bright", "loud"]
    my_password_4words = password_4words(nouns, verbs, adj)
    print("Test 2 - Password with 4 words:", my_password_4words)

    # Write another test for password_4words
    # ...

    # Test password_4words_better
    my_password_4words_better = password_4words_better(nouns, verbs, adj)
    print("Test 3 - Better Password with 4 words:", my_password_4words_better)

    # Write another test for password_4words_better
    # ...

if __name__ == "__main__":
    main()
