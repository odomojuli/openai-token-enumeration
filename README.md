# openai-token-enumeration
Enumeration of stable tokens

## Enumeration

```
import tiktoken
import sys

# Get the encoding for cl100k_base
enc = tiktoken.get_encoding("cl100k_base")

# Specify model (e.g gpt-3.5-turbo, gpt-4)
enc = tiktoken.encoding_for_model("gpt-4")

# List values for special tokens
# Compute range of values up-to first special token
# (ie 0-100256) or range(100257)

# Output values to text file
stdoutOrigin=sys.stdout 
sys.stdout = open("gpt-4.txt", "w")

# List values for special tokens
# Compute range of values up-to first special token
# (ie 0-100256) or range(100257)

for i in range(100256):
    stdoutOrigin.write(str(enc.decode_tokens_bytes([i]))+"\n")
for i in special_tokens:
    stdoutOrigin.write(str(enc.decode_tokens_bytes([i]))+"\n")

# Close session
stdoutOrigin.close()
```

# # Formatting

Strings are represented in byte-format using `enc.decode_tokens_bytes` to handle whitespace.

Strings may be alternatively represented using `enc.decode` to get raw output.
