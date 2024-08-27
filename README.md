����� Tailwind CSS ������������� ���������� ����� �������� ������ ������� ASP.NET, ����� ��������� �������� ������ (`batch script`) ��� PowerShell ������, ������� ������� �������� ������ CSS � ������� Tailwind, � ����� �������� ������ ASP.NET. 

���� ����������� PowerShell ������, ������� ������������� ��������� ������ CSS � ������� Tailwind CSS, � ����� ��������� ASP.NET ������.

### 1. **�������� ������������������� ������� ��� ������� ������� � Tailwind**

�������� ���� `run-project.ps1` � ����� ������ ������� � ����� ����������:

```powershell
# 1. ������ ������ CSS � ������� Tailwind CSS
npm run build:css

# 2. ������ ����������� ��� Tailwind CSS � ��������� ��������
Start-Process powershell -ArgumentList "-NoExit", "-Command", "npm run watch:css"

# 3. ������ ������� ASP.NET
dotnet watch run
```
### 2. ��������� �������

1. **���������� `package.json` ��� ���������� ������ ������ � ����������:**

���������, ��� � ��� ���� ��������� ������� � `package.json`:

```json
"scripts": {
  "build:css": "npx tailwindcss -i ./src/styles.css -o ./wwwroot/css/styles.css --minify",
  "watch:css": "npx tailwindcss -i ./src/styles.css -o ./wwwroot/css/styles.css --watch"
}
```
### 3. **������ ������������������� ����������**

��� ������� ������� �������� PowerShell � ���������:

```powershell
.\run-project.ps1
```
### 4. **�������������: �������� ����� ������� ��� ���� �����������**

����� ������� ������� ��� �����, �� ������ �������� �������� ��� ������� `run-project.ps1` � `package.json`. ��� �������� ��������� ��� � ������� ����� ������� npm.

� `package.json` �������� ��������� ������:
```json
"scripts": {
  "start": "powershell -ExecutionPolicy Bypass -File ./run-project.ps1"
}
```
������, ����� ������� ����� � ��������� ������, �� ������ ������������ ���� �������:

```bash
npm start
```
### 5. **������ ���������**

������ ������� `npm start` �������� ��������� ��������:
- ������� ����������� CSS � �������������� Tailwind.
- ����� �������� ������� ���������� �� ������� CSS.
- � �������, �������� ASP.NET ������.

���� ������ �������������� ���� �������, � ��� �� ����� ������������ � ������ CSS ����� �������� ASP.NET ������� � �� ���������� �������������.
