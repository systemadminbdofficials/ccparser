🚀 Features🔍 Smart Extraction: Automatically extracts card number, expiry date (MM/YY or MM/YYYY), and CVV from any input string.📏 Standardized Formatting: Converts messy card numbers into a clean xxxx xxxx xxxx xxxx format.✅ Luhn Validation: Verifies card numbers using the industry-standard Luhn algorithm.🗓️ Expiry & CVV Checks: Validates expiration dates and CVV length based on the specific card type.💳 Card Type Detection: Identifies major networks (Visa, MasterCard, AMEX, Discover, JCB, etc.).🔒 Masked Output: Securely displays card numbers (e.g., **** **** **** 5379).🔗 Flexible Delimiters: Supports parsing strings separated by |, :, or spaces.🆕 Card Generation: Generate valid card numbers for testing and development purposes.🖥️ Command-Line Support: Includes a CLI tool for rapid terminal-based parsing.💳 Supported Card TypesCCParser uses advanced regex patterns to accurately identify card providers:ProviderRegex Pattern (Simplified)Visa^4[0-9]{12}(?:[0-9]{3})?$MasterCard^5[1-5][0-9]{14}$AMEX^3[47][0-9]{13}$Discover`^6(?:011JCB`^(?:2131Diners Club`^3(?:0[0-5]UnionPay^62[0-9]{14,17}$📥 InstallationInstall the package directly via PyPI:Bashpip install ccparser
📝 Usage ExamplesSupported Input FormatsCCParser is highly flexible and accepts various input styles:4111111111111111|12/30|1234111111111111111:12:30:1234111111111111111 12 2030 123Python APIPythonfrom ccparser import CCParser

# Initialize with a raw string
card = CCParser("4111111111111111|12|2030|123")

print(card.get_formatted_number()) # 4111 1111 1111 1111
print(card.get_expiry())           # 12/30
print(card.get_card_type())        # Visa
print(card.is_valid())             # True
print(card.get_masked_number())    # **** **** **** 1111
Card Number GenerationPythonfrom ccparser.generator import generate_card_number

print(generate_card_number("Visa"))       # Generates a valid Visa
print(generate_card_number("MasterCard")) # Generates a valid MasterCard
CLI ToolBashccparser "4111111111111111|12|2030|123"
⚠️ DisclaimerThis library is intended for educational and legitimate development purposes only.Prohibited Uses:Unauthorized access to financial data.Credit card fraud or "carding" activities.Storing or processing stolen card information.By using this library, you agree to comply with all applicable laws, including PCI-DSS standards. The author(s) are not responsible for any misuse or illegal activities conducted with this tool.🛠️ Development & CI/CDTesting: Automated tests via GitHub Actions.Distribution: Ready for PyPI.Documentation: Built with Markdown for easy reading.
