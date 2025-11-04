**Creating Tables in JSON Adaptive Cards**

Tables Schema Explorer | Adaptive Cards
https://adaptivecards.io/explorer/Table.html

See video Dynamically Fill Adaptive Card with Azure Table Content in Copilot Studio

https://www.youtube.com/watch?v=QjhymlCZtXc 

{
    "myArrayData": [
        { "Name": "Alice", "ID": "1001" },
        { "Name": "Bob", "ID": "1002" },
        { "Name": "Charlie", "ID": "1003" }
    ]
}

{
    "type": "AdaptiveCard",
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.5",
    "body": [
        {
            "type": "Table",
            "showGridLines": true,
            "firstRowAsHeader": true,
            "columns": [
                { "width": 100 },
                { "width": 100 }
            ],
            "rows": [
                {
                    "type": "TableRow",
                    "cells": [
                        { "type": "TableCell", "items": [ { "type": "TextBlock", "text": "Employee Name", "weight": "Bolder" } ] },
                        { "type": "TableCell", "items": [ { "type": "TextBlock", "text": "Employee ID", "weight": "Bolder" } ] }
                    ]
                },
                {
                    "$data": "${myArrayData}",
                    "type": "TableRow",
                    "cells": [
                        { "type": "TableCell", "items": [ { "type": "TextBlock", "text": "${Name}" } ] },
                        { "type": "TableCell", "items": [ { "type": "TextBlock", "text": "${ID}" } ] }
                    ]
                }
            ]
        }
    ]
}
