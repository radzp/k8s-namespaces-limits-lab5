# k8s-namespaces-limits-lab5
# Laboratorium 5: 

## Utworzenie przestrzeni nazw

Najpierw stworzone zostały przestrzenie nazw `ns-dev` i `ns-prod`.

<img width="351" height="143" alt="Zrzut ekranu 2025-11-11 o 12 19 19 AM" src="https://github.com/user-attachments/assets/a5ddcfe6-994f-4ad8-b4f4-b89029a23dc1" />

<img width="324" height="183" alt="Zrzut ekranu 2025-11-11 o 12 20 20 AM" src="https://github.com/user-attachments/assets/9d400e5e-ae7e-450d-95b5-a2293d15d2df" />

## Konfiguracja Zasobów
### Utworzyłam polityki zarządzania zasobami dla obu przestrzeni.

<img width="301" height="167" alt="Zrzut ekranu 2025-11-11 o 12 22 16 AM" src="https://github.com/user-attachments/assets/78ec4ee8-4912-4fc9-8901-10698bb85871" />
<img width="353" height="143" alt="Zrzut ekranu 2025-11-11 o 12 22 50 AM" src="https://github.com/user-attachments/assets/2d70e3d1-021c-46fd-9837-72e7966f5a08" />

<img width="334" height="341" alt="Zrzut ekranu 2025-11-11 o 12 23 40 AM" src="https://github.com/user-attachments/assets/e2548ac4-ac33-4f2f-a688-00f354d3e4aa" />

<img width="324" height="336" alt="Zrzut ekranu 2025-11-11 o 12 24 10 AM" src="https://github.com/user-attachments/assets/a638d2c2-7994-4758-8a12-53972ec7beb9" />

<img width="300" height="423" alt="Zrzut ekranu 2025-11-11 o 12 24 33 AM" src="https://github.com/user-attachments/assets/698dd6d2-2a9f-494b-801a-c24ac59d3557" />

### Weryfikacje:
<img width="724" height="102" alt="Zrzut ekranu 2025-11-11 o 12 26 32 AM" src="https://github.com/user-attachments/assets/030ba351-30c5-435c-9f3e-ad105e58aeb6" />

<img width="732" height="108" alt="Zrzut ekranu 2025-11-11 o 12 26 58 AM" src="https://github.com/user-attachments/assets/b1b23ce7-9a52-4752-9478-7d7e8a8eb947" />

<img width="732" height="182" alt="Zrzut ekranu 2025-11-11 o 12 28 00 AM" src="https://github.com/user-attachments/assets/53a96139-ec1d-48f5-9e72-af7e05410f58" />

## Deployment no-test, który przekroczy limity 
<img width="730" height="53" alt="Zrzut ekranu 2025-11-11 o 12 28 28 AM" src="https://github.com/user-attachments/assets/bd186973-32d0-457e-a0e5-b1a26874e52c" />

### no-test-deploy.yaml:
<img width="742" height="639" alt="Zrzut ekranu 2025-11-11 o 12 29 40 AM" src="https://github.com/user-attachments/assets/acfcc004-923a-4789-aa81-27a82e8300fb" />

<img width="615" height="207" alt="Zrzut ekranu 2025-11-11 o 12 31 03 AM" src="https://github.com/user-attachments/assets/97e30ce0-4668-4b12-b129-909a26a438a5" />

#### Przy użyciu: 
`kubectl describe rs no-test-79fb9d8bd -n ns-dev`

<img width="782" height="119" alt="Zrzut ekranu 2025-11-11 o 12 31 58 AM" src="https://github.com/user-attachments/assets/11b4453e-f33e-4295-a99a-e564340bb843" />

#### otrzymujemy informację potwierdzającą założenie w zadaniu.

## Deployment yes-test zgodnie z limitami

<img width="759" height="55" alt="Zrzut ekranu 2025-11-11 o 12 32 47 AM" src="https://github.com/user-attachments/assets/202aba03-2f16-4424-9f77-d10d773a8d60" />

### yes-test-deploy.yaml:
<img width="798" height="646" alt="Zrzut ekranu 2025-11-11 o 12 33 34 AM" src="https://github.com/user-attachments/assets/7ff5b0c1-eaa3-4ede-b272-a20b6fbee8e6" />

<img width="564" height="176" alt="Zrzut ekranu 2025-11-11 o 12 34 14 AM" src="https://github.com/user-attachments/assets/3d51f1c0-feb2-47f7-bbec-4e5388dc1315" />

### Sukces-status Running
## Potwierdzenie zajętych zasobów:
<img width="759" height="114" alt="Zrzut ekranu 2025-11-11 o 12 35 04 AM" src="https://github.com/user-attachments/assets/e74b29b3-79fa-4842-9e10-0a3246d0acbd" />

## Deployment zero-test, bez żadnych deklarowanych zasobów
<img width="758" height="51" alt="Zrzut ekranu 2025-11-11 o 12 36 05 AM" src="https://github.com/user-attachments/assets/34e1f9b7-4ebf-4577-9db5-e3988b732bd5" />

### zero-test-deploy.yaml
<img width="766" height="542" alt="Zrzut ekranu 2025-11-11 o 12 36 36 AM" src="https://github.com/user-attachments/assets/f4bfb2e6-6f15-48de-84ec-a59f4075de9a" />

<img width="587" height="66" alt="Zrzut ekranu 2025-11-11 o 12 36 19 AM" src="https://github.com/user-attachments/assets/089c81a9-2775-4593-99b8-aa43a5bd05df" />

<img width="580" height="94" alt="Zrzut ekranu 2025-11-11 o 12 37 19 AM" src="https://github.com/user-attachments/assets/a29c072c-4afb-4a8b-a17f-a8206ba48130" />

## Sekcja Containers w wyniku z polecenia describe:
<img width="636" height="212" alt="Zrzut ekranu 2025-11-11 o 12 37 38 AM" src="https://github.com/user-attachments/assets/4c615e96-4a92-44fc-b60f-2ee8e5930e18" />



