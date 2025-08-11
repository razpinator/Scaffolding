# Scaffolding

This repository contains the code for the following features.
 
## ASP.NET Scaffolding
ASP.NET scaffolding: this can be used to generate boilerplate code for web apps to improve developer productivity

For more info on ASP.NET scaffolding, see the scaffolding readme here at [README](./src/Scaffolding/README.md)

### Tailwind CSS Template Updates

The scaffolding templates have been modernized with Tailwind CSS to provide a more contemporary and responsive user interface. The following changes have been implemented:

#### **Updated Templates**
- **Create.cshtml** - Modern form design with improved validation styling and user experience
- **Delete.cshtml** - Enhanced confirmation page with warning alerts and clear action buttons
- **Details.cshtml** - Professional data display with gradient headers and organized layout
- **Edit.cshtml** - Streamlined editing interface with visual feedback and clear actions
- **Empty.cshtml** - Helpful starter template with guidance for developers
- **List.cshtml** - Modern data table with responsive design and styled action buttons
- **_Layout.cshtml** - Updated navigation and responsive layout framework

#### **Key Improvements**
- **Modern Design**: Contemporary UI with professional color schemes and typography
- **Responsive Layout**: Mobile-first design that works across all device sizes
- **Enhanced UX**: Improved form validation, hover effects, and visual feedback
- **Accessibility**: Better contrast ratios, focus management, and screen reader support
- **Performance**: Optimized with Tailwind CSS CDN for fast loading
- **Consistency**: Unified design system across all CRUD operations

#### **Technical Changes**
- Replaced Bootstrap classes with Tailwind CSS utility classes
- Added SVG icons for better visual communication
- Implemented modern card-based layouts with shadows and rounded corners
- Enhanced form controls with focus states and validation styling
- Improved data tables with hover effects and better organization
- Added responsive navigation with mobile menu functionality

#### **Implementation**
Templates support both layout-based and standalone scenarios:
- **With Layout**: Seamlessly integrates with the updated `_Layout.cshtml`
- **Standalone**: Includes complete HTML structure with Tailwind CSS CDN
- **Backward Compatible**: Maintains all existing ASP.NET Core functionality

The updated templates provide a modern, professional appearance while maintaining full compatibility with existing ASP.NET Core scaffolding workflows.

#### **How to Add These Templates to Your ASP.NET Project**

There are several ways to integrate these Tailwind CSS templates into your ASP.NET project:

##### **Method 1: Custom Scaffolding Templates (Recommended)**

1. **Create the CodeTemplates folder structure** in your ASP.NET project:
   ```
   YourProject/
   ├── CodeTemplates/
       └── MvcView/
           ├── Create.cshtml
           ├── Delete.cshtml
           ├── Details.cshtml
           ├── Edit.cshtml
           ├── Empty.cshtml
           ├── List.cshtml
           └── _Layout.cshtml
   ```

2. **Copy the template files** from this repository into the corresponding files in your `CodeTemplates/MvcView/` folder

3. **Update your main layout** by replacing `Views/Shared/_Layout.cshtml` with the Tailwind CSS version, or add Tailwind CSS to your existing layout:
   ```html
   <!-- Add to your _Layout.cshtml head section -->
   <script src="https://cdn.tailwindcss.com"></script>
   ```

4. **Scaffold new controllers/views** - Visual Studio will automatically use your custom templates

##### **Method 2: Manual Template Integration**

1. **Add Tailwind CSS** to your existing `_Layout.cshtml`:
   ```html
   <script src="https://cdn.tailwindcss.com"></script>
   ```

2. **For new views**: After scaffolding, replace the generated view content with the Tailwind versions

3. **For existing views**: Backup your current views and replace with the modernized templates

##### **Method 3: Production Setup with Build Process**

1. **Install Tailwind CSS via NPM**:
   ```bash
   npm install -D tailwindcss
   npx tailwindcss init
   ```

2. **Configure Tailwind** in your build process instead of using the CDN

3. **Copy the templates** as described in Method 1

##### **Template Customization**

When copying templates, update the placeholder values to match your models:
- Replace `@Model.ViewDataTypeName` with your actual model type (e.g., `Product`)
- Replace `@Model.ViewDataTypeShortName` with your entity name
- Replace `@Model.ViewName` with your view name

**Example for a Product model:**
```razor
@model Product  // Instead of @@model @Model.ViewDataTypeName
```

##### **Validation Scripts**

Ensure your project includes jQuery validation scripts by adding to your layout or specific views:
```html
@section Scripts {
    @await Html.RenderPartialAsync("_ValidationScriptsPartial")
}
```

##### **Testing Your Implementation**

1. Create a test controller to verify the templates work correctly
2. Navigate to each CRUD action to ensure Tailwind styling loads properly
3. Test responsive behavior on different screen sizes
4. Verify form validation and user interactions function as expected

The templates will provide a modern, responsive interface for your ASP.NET CRUD operations with professional styling and improved user experience.

## `dotnet msidentity`
This is a .NET tool which can be used to configure ASP.NET Core projects to use the [Microsoft identity platform](https://docs.microsoft.com/en-us/azure/active-directory/develop/). 
The tool can be used to configure ASP.NET Core projects to authenticate with the Microsoft identity platform.

For more info on the `dotnet msidentity` tool, see the readme here at [README](./src/MSIdentityScaffolding/README.md)

## Reporting security issues and bugs

Security issues and bugs should be reported privately, via email, to the Microsoft Security Response Center (MSRC)  secure@microsoft.com. You should receive a response within 24 hours. If for some reason you do not, please follow up via email to ensure we received your original message. Further information, including the MSRC PGP key, can be found in the [Security TechCenter](https://technet.microsoft.com/en-us/security/ff852094.aspx).

## Related projects

These are some other repos for related projects:
* [Microsoft Identity Web](https://github.com/AzureAD/microsoft-identity-web) - is a library which contains a set of reusable classes used in conjunction with ASP.NET Core for integrating with the [Microsoft identity platform](https://docs.microsoft.com/en-us/azure/active-directory/develop/) (formerly *Azure AD v2.0 endpoint*) and [AAD B2C](https://docs.microsoft.com/en-us/azure/active-directory-b2c/).
* [EF Core](https://github.com/dotnet/efcore) - source for [Entity Framework Core](https://docs.microsoft.com/en-us/ef/core/)

## Code of conduct

See [CODE-OF-CONDUCT](./CODE-OF-CONDUCT.md)