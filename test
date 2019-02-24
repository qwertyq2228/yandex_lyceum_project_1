import string

morse_zip = zip(
    tuple(string.ascii_letters[26:] + string.digits + '.,:;\'\"-/?! '),
    ('.-', '-...', '-.-.', '-..', '.', '..-.', '--.', '....', '..', '.---', '-.-', '.-..', '--', '-.', '---', '.--.',
        '--.-', '.-.', '...', '-', '..-', '...-', '.--', '-..-', '-.--', '--..',
        '-----', '.----', '..---', '...--', '....-', '.....', '-....', '--...', '---..', '----.',
        '......', '.-.-.-', '---...', '-.-.-.', '.----.', '.-..-.', '-....-', '-..-.', '..--..', '--...--', '-..-'
     )
)

MorseCode = dict(morse_zip)
MorseUnCode = {d:k for k, d in MorseCode.items()}


def decode_from_morse(code):
    if not set(code.split()).issubset(set(MorseUnCode.keys())):
        return False
    return ''.join([MorseUnCode[elem] for elem in code.split()])


def encode_to_morse(text):
    global MorseCode
    s = ''
    for i in text.upper():
        if i not in MorseCode.keys():
            return False
        s += MorseCode[i] + " "
    return s[:-1]


def main():
    text = input('Введите текст\n')
    q = input('Вы хотите кодировать или декодировать текст?\n').lower()
    while q != 'кодировать' and q != 'декодировать':
        q = input('Ой! Вы что-то ввели не так, попробуйте еще раз\n').lower()
    if q == 'кодировать':   
        ans = encode_to_morse(text)
    else:
        ans = decode_from_morse(text)
    if ans:
        print(ans)
    else:
        print('Вы ввели символ, не предусмотренный азбукой Морзе. Попробуйте ещё раз')
        main()


# print(decode_from_morse('.... . .-.. .-.. --- .-.-.- -..- -.-. --- -.-. -.- --...--'))
# print(encode_to_morse('Hello, bro!'))
