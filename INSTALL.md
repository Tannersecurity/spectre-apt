# Spectre installieren (Ubuntu/Debian)

1. Schluessel holen und pruefen:

       sudo mkdir -p /etc/apt/keyrings
       curl -fsSL https://tannersecurity.github.io/spectre-apt/spectre-archive-keyring.gpg | sudo tee /etc/apt/keyrings/spectre.gpg >/dev/null
       gpg --show-keys --with-fingerprint /etc/apt/keyrings/spectre.gpg

   Der Fingerabdruck muss `FDD3 6A9A 0A6A DA48 2B30  948A E2F8 0150 0521 1A00` sein. Sonst: `sudo rm /etc/apt/keyrings/spectre.gpg` und nicht weitermachen.

2. Archiv eintragen und installieren:

       echo "deb [signed-by=/etc/apt/keyrings/spectre.gpg] https://tannersecurity.github.io/spectre-apt stable main" | sudo tee /etc/apt/sources.list.d/spectre.list
       sudo apt update
       sudo apt install spectre
       spectre init

Entfernen: `sudo apt remove spectre`, danach optional `sudo rm /etc/apt/sources.list.d/spectre.list /etc/apt/keyrings/spectre.gpg`.
