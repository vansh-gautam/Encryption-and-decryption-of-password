alphabet=['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z']
direction=input("Type 'encode' to encrypt or 'decode' to dcrypt\n").lower()
text=input("Enter the original text: \n")
shift=int(input("Enter the number by which you want to shift letters: \n"))

def encrypt(original_text, shift_amount):
    cipher_text=""
    for letter in original_text:
        shifted_position=alphabet.index(letter)+shift_amount
        shifted_position=shifted_position%len(alphabet) # this is to make sure we are in range 0-25 like if we
        cipher_text+=alphabet[shifted_position] # shift z by no. 2 it will give b

    print(f"here is the encoded result: {cipher_text}")

#encrypt(original_text=text,shift_amount=shift)

def decrypt(original_text, shift_amount):
    decipher_text=""
    for element in original_text:
        shifted_back=alphabet.index(element)-shift_amount
        shifted_back%=len(alphabet)
        decipher_text+=alphabet[shifted_back]

    print(f"here is the decoded result:{decipher_text}")

def ceaser(original_text,shift_amount,encode_or_decode):
    output_text = ""
    if encode_or_decode == "decode":
        shift_amount *= -1
    for letter in original_text:

        if letter not in alphabet:
            output_text+=letter
        else:


        #else:
            #shift_amount*=1

            shifted_position = alphabet.index(letter) + shift_amount
            shifted_position %= len(alphabet)
            output_text += alphabet[shifted_position]

    print(f"here is the {encode_or_decode}d result:{output_text}")
should_continue=True
while should_continue:
    direction = input("Type 'encode' to encrypt or 'decode' to dcrypt\n").lower()
    text = input("Enter the original text: \n")
    shift = int(input("Enter the number by which you want to shift letters: \n"))

    ceaser(original_text=text,shift_amount=shift,encode_or_decode=direction)

    restart=input("Type 'yes' if you want to continue or 'no'\n").lower()
    if restart=='no':
        should_continue=False
        print("See you")
