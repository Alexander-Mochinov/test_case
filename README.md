# test_case
```python

numbers_dict = {
    "2": "abc",
    "3": "def",
    "4": "ghi",
    "5": "jkl",
    "6": "mno",
    "7": "pqrs",
    "8": "tuv",
    "9": "wxyz",
}

def solve(numbers: str) -> list:
    
    result_list = []

    if len(numbers) == 1:
        return [_ for _ in numbers_dict[numbers[0]]]

    def combinator(
        digits: int, 
        result: list, 
        current_string: str = "", 
        current_level:int = 0,
    ) -> list:
        """
        Комбенирование списков
        """
        if current_level == len(digits):
            result.append(current_string)
            return result

        for index in numbers_dict[digits[current_level]]:
            combinator(
                digits, 
                result, 
                current_string + index,
                current_level + 1,
            )

        return result

    result_list = combinator(
        digits = numbers,
        result = result_list,
    )

    return result_list

print(solve("23")) # ['ad', 'ae', 'af', 'bd', 'be', 'bf', 'cd', 'ce', 'cf']
print(solve("237")) # ['adp', 'adq', 'adr', 'ads', 'aep', 'aeq', 'aer', 'aes', 'afp', 'afq', 'afr', 'afs', 'bdp', 'bdq', 'bdr', 'bds', 'bep', 'beq', 'ber', 'bes', 'bfp', 'bfq', 'bfr', 'bfs', 'cdp', 'cdq', 'cdr', 'cds', 'cep', 'ceq', 'cer', 'ces', 'cfp', 'cfq', 'cfr', 'cfs']


```
