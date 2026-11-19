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
- Step 4.6, tool and calories of the answer of POST /api/pizza:
  Tool: Pizza cutter, Calories: 400
- Step 4.7, the line of the admin list that shows your pizza:
  Lab Pizza 20261119-210922 (tool=Pizza cutter, ingredients_number=6) (newest)
- Step 4.8, run 1, result, duration and pizza name:
  1 passing, 12 seconds, Lab Pizza 20261119-211632
- Step 4.8, run 2, result, duration and pizza name:
  1 passing, 13 seconds, Lab Pizza 20261119-211940

## Part B

1. ใช้ Label เพราะช่องตัวเลขมี id ซ้ำกัน ทำให้เลือกช่องผิดได้ ถ้าเพิ่ม id ที่ไม่ซ้ำกันให้แต่ละช่อง จะทำให้เขียน Test และเลือก Element ได้ง่ายขึ้น

2. เป็น Consistency Oracle เพราะใช้เปรียบเทียบ Tool ระหว่างหน้า Recommendation กับหน้า Admin ถ้าข้อมูลสองหน้าไม่ตรงกัน เช่น หน้าแรกแสดง Pizza cutter แต่หน้า Admin แสดง Scissors จะสามารถตรวจพบความผิดพลาดได้

3. เพิ่มการตรวจสอบค่า `vegetarian` ใน API Response ว่าต้องเป็น `true` โดยต้องเข้าถึงข้อมูลจาก API หรือมีสถานะ Vegetarian แสดงบนหน้าเว็บ

4. ทั้งสอง Tools สามารถรอ Element ได้โดยไม่ต้องใช้ Fixed Delay โดย Robot Framework ใช้ SeleniumLibrary ส่วน Cypress มี Automatic Retry ทำให้เขียน Test ได้สะดวก นอกจากนี้ Cypress มี Screenshots และ Video ช่วยตรวจสอบผลการทำงานได้ง่ายกว่า

5. เลือก Cypress เพราะมี Automatic Retry ช่วยลดปัญหาการรอ Element และมี Screenshots กับ Video สำหรับตรวจสอบข้อผิดพลาด อีกทั้งยังสามารถใช้ Intercept เพื่อตรวจสอบ API Request และ Response ได้ด้วย

6. หาก Locator ของ Calories เปลี่ยน จะต้องแก้ที่ Resource File เท่านั้น ส่วน Test File ไม่ต้องแก้ เพราะเรียกใช้ Keyword จาก Resource File ทำให้แก้ไขและดูแล Test ได้ง่ายขึ้น

7. QP-01 ต้องอยู่ใน Test เดียวกัน เพราะ Cypress จะ Clear Cookies ก่อนเริ่มแต่ละ Test ซึ่ง Cookies ช่วยให้ Browser เชื่อมต่อกับ Server เดิม หากแยก Step 6 และ 7 เป็นอีก Test อาจทำให้เชื่อมต่อคนละ Server และไม่พบ Pizza ที่สร้างไว้