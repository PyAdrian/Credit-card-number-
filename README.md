# Credit-card-number-

import re

for _ in range(int(input())):
    s = input()
    no_hyphen = s.replace('-', '')
    print("Valid" if (re.match(r'^[456]', s) and
                      re.match(r'^[0-9]{16}$', no_hyphen) and
                      not re.search(r'([0-9])\1{3}', no_hyphen) and
                      not re.search(r'(?<![0-9]{4})-', s) and
                      not re.search(r'-(?![0-9]{4})', s))
          else "Invalid")
