# Steps to Publish NuGet Packages into a NuGet Feed

There are two options for publishing NuGet packages into a NuGet feed:

## Option 1: Publish a Specific NuGet Package

**Note:** Before starting, ensure that all required dependency packages are available in the feed.

### Step-by-Step Guide

1. **Download the NuGet Package:**
   - Go to the NuGet website: [https://www.nuget.org](https://www.nuget.org).
   - Search for and download the package you need (e.g., `System.Text.Json` version `6.0.10`).
   - Save the package in a folder, such as your `Downloads` folder.

2. **Verify Dependencies:**
   - Make sure that all dependencies for your package are present in the feed (e.g., `LandaFeed01`). If any are missing, add them before proceeding.

3. **Add the `nuget.config` File:**
   - Place a `nuget.config` file in the same folder where you saved the package (e.g., the `Downloads` folder).

4. **Run the Publish Command:**
   - Open a command prompt and navigate to the folder where the package and `nuget.config` file are located.
   - Run the following command to publish the NuGet package into your specified feed:

     ```bash
     nuget.exe push -Source <YourFeedName> -ApiKey az <packagePath>
     ```

   - Replace `<YourFeedName>` with the name of your feed (e.g., `LandaFeed01`).
   - Replace `<packagePath>` with the exact filename of your NuGet package (e.g., `system.text.json.6.0.10.nupkg`).

### Additional Notes

- **Dependency Check:** Ensure all dependencies are available in the feed to avoid issues during package installation.
- **`nuget.config` File:** Make sure this file is correctly configured for your specified feed.
