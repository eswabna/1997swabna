# 1997swabna



def decode_matrix(matrix):
  """Decodes the given matrix of strings and returns the decoded text.

  Args:
    matrix: A list of strings, where each string is a row of the matrix.

  Returns:
    A string containing the decoded text.
  """

  decoded_text = ""
  for column in range(len(matrix[0])):
    decoded_column_text = ""
    for row in range(len(matrix)):
      current_character = matrix[row][column]
      if current_character.isalnum():
        decoded_column_text += current_character
      else:
        decoded_column_text += " "

    
    decoded_column_text = " ".join(decoded_column_text.split())

    decoded_text += decoded_column_text + " "

  return decoded_text


def main():
  """Reads the matrix from the user and prints the decoded text to the console."""

  
  n, m = map(int, input("Enter the dimensions of the matrix (N and M): ").split())

 
  matrix = []
  for i in range(n):
    matrix.append(input("Enter row {}: ".format(i + 1)))

  
  decoded_text = decode_matrix(matrix)
  print("The decoded text is: {}".format(decoded_text))


if __name__ == "__main__":
  main()
