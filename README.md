# TryPlayWright

A comprehensive .NET web application demonstrating Playwright functionality with JavaScript examples, complete with CI/CD via GitHub Actions.

## 🎭 About This Project

This ASP.NET Core web application showcases all the major features of Playwright, a powerful end-to-end testing framework. The application provides interactive examples that can be automated using Playwright for testing purposes.

## ✨ Features Demonstrated

- **🎯 Selectors & Locators**: CSS selectors, XPath, text-based selectors, role-based selectors
- **🖱️ User Interactions**: Clicks, double-clicks, hover, drag & drop, keyboard input
- **📝 Form Handling**: Text inputs, checkboxes, radio buttons, dropdowns, file uploads
- **🚀 Navigation & Waits**: Page navigation, dynamic content loading, waiting strategies
- **📸 Screenshots & Traces**: Visual regression testing, trace recording for debugging
- **🎭 Dialog & Alerts**: Browser alerts, confirms, prompts, and custom modals

## 🛠️ Technology Stack

- **Backend**: ASP.NET Core 8.0 with Razor Pages
- **Frontend**: Bootstrap 5, JavaScript
- **Testing Framework**: Playwright (examples in JavaScript)
- **CI/CD**: GitHub Actions

## 🚀 Getting Started

### Prerequisites

- [.NET 8.0 SDK](https://dotnet.microsoft.com/download) or later
- A modern web browser
- (Optional) [Playwright](https://playwright.dev/) for running automated tests

### Running the Application

1. Clone the repository:
```bash
git clone https://github.com/cardze/TryPlayWright.git
cd TryPlayWright
```

2. Navigate to the project directory:
```bash
cd PlaywrightDemo
```

3. Restore dependencies:
```bash
dotnet restore
```

4. Run the application:
```bash
dotnet run
```

5. Open your browser and navigate to:
```
https://localhost:5001
```
or
```
http://localhost:5000
```

### Building for Production

```bash
dotnet build --configuration Release
dotnet publish --configuration Release --output ./publish
```

## 🧪 Using Playwright with This Application

### Install Playwright

**For JavaScript/TypeScript:**
```bash
npm init playwright@latest
```

**For .NET:**
```bash
dotnet add package Microsoft.Playwright
pwsh bin/Debug/net8.0/playwright.ps1 install
```

### Example Test Script (JavaScript)

```javascript
const { test, expect } = require('@playwright/test');

test('test selectors page', async ({ page }) => {
  // Navigate to the app
  await page.goto('http://localhost:5000/Selectors');
  
  // Test CSS selector
  await page.locator('#btn-primary').click();
  
  // Test text selector
  await page.getByText('Click Me').click();
  
  // Take a screenshot
  await page.screenshot({ path: 'selectors-test.png' });
});

test('test form handling', async ({ page }) => {
  await page.goto('http://localhost:5000/Forms');
  
  // Fill form
  await page.locator('#name').fill('John Doe');
  await page.locator('#email').fill('john@example.com');
  
  // Select checkbox
  await page.locator('#interest-coding').check();
  
  // Select radio button
  await page.locator('#exp-intermediate').check();
  
  // Select dropdown
  await page.locator('#country').selectOption('us');
  
  // Submit form
  await page.locator('button[type="submit"]').click();
  
  // Verify result
  await expect(page.locator('#form-result')).toBeVisible();
});
```

## 📁 Project Structure

```
TryPlayWright/
├── .github/
│   └── workflows/
│       └── dotnet-ci.yml       # GitHub Actions CI/CD workflow
├── PlaywrightDemo/
│   ├── Pages/
│   │   ├── Index.cshtml        # Home page with feature overview
│   │   ├── Selectors.cshtml    # Selector demonstrations
│   │   ├── Interactions.cshtml # User interaction examples
│   │   ├── Forms.cshtml        # Form handling examples
│   │   ├── Navigation.cshtml   # Navigation and wait examples
│   │   ├── Screenshots.cshtml  # Screenshot and trace examples
│   │   ├── Dialogs.cshtml      # Dialog handling examples
│   │   └── Shared/
│   │       └── _Layout.cshtml  # Main layout
│   ├── wwwroot/                # Static files (CSS, JS, images)
│   ├── Program.cs              # Application entry point
│   └── PlaywrightDemo.csproj   # Project file
└── README.md
```

## 🔄 CI/CD Pipeline

The project includes a GitHub Actions workflow that automatically:

1. **Build**: Compiles the .NET application
2. **Test**: Runs all unit tests (when available)
3. **Publish**: Creates deployment artifacts
4. **Deploy**: Deploys to staging/production (configurable)

The workflow is triggered on:
- Push to `main`, `master`, or `develop` branches
- Pull requests to these branches
- Manual workflow dispatch

## 📚 Learn More

- [Playwright Documentation](https://playwright.dev/)
- [ASP.NET Core Documentation](https://docs.microsoft.com/aspnet/core/)
- [GitHub Actions Documentation](https://docs.github.com/actions)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is open source and available for educational purposes.

## 👨‍💻 Author

Created to demonstrate Playwright testing capabilities with a .NET web application.

---

**Happy Testing! 🎭**
