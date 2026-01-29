# PowerShell Script to generate Credit Plus website
$folderPath = "C:\CreditPlusSite"
$filePath = "$folderPath\index.html"

# Create folder if not exists
if (!(Test-Path -Path $folderPath)) {
    New-Item -ItemType Directory -Path $folderPath
}

# HTML content
$htmlContent = @"
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Credit Plus</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 0; padding: 0; background: #f4f4f4; }
        header { background: #2c3e50; color: white; padding: 20px; text-align: center; }
        section { padding: 20px; margin: 20px; background: white; border-radius: 8px; }
        footer { background: #2c3e50; color: white; text-align: center; padding: 10px; }
        h1, h2 { color: #2c3e50; }
        a { color: #2980b9; text-decoration: none; }
    </style>
</head>
<body>
    <header>
        <h1>Credit Plus</h1>
        <p>Your trusted partner for financial support</p>
    </header>

    <section>
        <h2>About Us</h2>
        <p>Credit Plus provides fast and reliable loan services tailored to your needs. 
        Whether for personal or business purposes, we ensure transparency and efficiency in every transaction.</p>
    </section>

    <section>
        <h2>Contact</h2>
        <p>Email us at: <a href="mailto:creditplus@gmail.com">creditplus@gmail.com</a></p>
    </section>

    <section>
        <h2>Legal Disclaimer</h2>
        <p>Credit Plus is a financial service provider. All loans are subject to approval and terms & conditions. 
        Borrow responsibly. This website does not constitute financial advice. Please consult a licensed advisor before making financial decisions.</p>
    </section>

    <footer>
        <p>&copy; 2026 Credit Plus. All rights reserved.</p>
    </footer>
</body>
</html>
"@

# Write HTML file
Set-Content -Path $filePath -Value $htmlContent -Encoding UTF8

Write-Output "Website generated successfully at $filePath"

