# UI lab results

Tool parts that I chose: Part 3 and Part 4

## Part 0
- Step 0.1, Chrome version: 157.0.8103.79
- Step 0.3, ChromeDriver version: 157.0.8103.79
- Step 0.4, locator of Pizza, Please!: name=pizza-please
- Step 0.4, locator of Excluded tools: css=select[multiple]
- Step 0.4, locator of Must be vegetarian: id=default-checkbox
- Step 0.4, locator of Custom Pizza Name: input#pizza-name
- Step 0.5, pizza name, tool and calories of the run by hand:
  Lab Pizza 20261119-130045, Pizza cutter, 475

| Step | Actual result | Pass or fail |
|------|---------------|--------------|
| 1 | Heading displayed correctly | Pass |
| 2 | Advanced fields appeared | Pass |
| 3 | 600 calories, Knife excluded, vegetarian checked, custom name entered | Pass |
| 4 | Lab Pizza 20261119-130045, Pizza cutter, 475 calories | Pass |
| 5 | Please log in first. displayed | Pass |
| 6 | Latest pizza recommendations displayed | Pass |
| 7 | Lab Pizza 20261119-130045 found in admin list, tool=Pizza cutter | Pass |

## Part 3: Robot Framework
- robot --version: Robot Framework 7.5.1 (Python 3.10.4 on win32)
- Step 3.2, failure message for the wrong title:
  Title should have been 'Web Form' but was 'Web form'.
- Step 3.8, run 1, result, elapsed time and pizza name:
  PASS, 00:00:17.592, Lab Pizza 20261119-194540
- Step 3.8, run 2, result, elapsed time and pizza name:
  PASS, 00:00:19.178, Lab Pizza 20261119-194650

## Part 4: Cypress
- node --version: v22.20.0
- npm --version: 10.9.3
- npx cypress version: 16.2.1
- Step 4.3, wrong title failure message:
  Expected: Web Form
  Actual: Web form
- Step 4.3, corrected title result:
  PASS, 1 passing, 0 failing