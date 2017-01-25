#!/usr/bin/python3

import requests, json, sys
from datetime import datetime

DAYS = {
    0: 'Poniedziałek',
    1: 'Wtorek',
    2: 'Środa',
    3: 'Czwartek',
    4: 'Piątek'
}

if __name__ == '__main__':
    # get data
    response = requests.get('http://ssh.autism-gamers.tk:5000/menu.json')
    data = json.loads(response.text)
    
    if len(sys.argv) > 1:
        if sys.argv[1] == 'today':
            weekday = datetime.today().weekday()
            if weekday > 4:
                print('Jest weekend. Nie ma obiadu!')
            else:
                print('Dzisiaj:')
                for dish in data[weekday]:
                    print('\t' + dish)
        else:
            print('Nie rozpoznano argumentu')
        
    else:
        # And a loop for printing everything
        for day in range(len(data)):
            print(DAYS[day] + ':')
            for dish in data[day]:
                print('\t' + dish)
            # extra line
            print()