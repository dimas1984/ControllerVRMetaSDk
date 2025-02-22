# Tutorial Setting Controller VR menggunakan Meta SDK

## Prerequisites

Sebelum memulai, pastikan Anda memiliki perangkat lunak berikut terinstal:

- [Unity Hub](https://unity.com/download)
- [Visual Studio](https://visualstudio.microsoft.com/) 
- [Asset Store Meta XR All-In-One SDK](https://assetstore.unity.com/search#q=meta%20xr%20all-in-one%20sdk)

## Langkah 1: Membuat Proyek Baru ( menggunakan Unity version 6000.0.38f1)

1. Buka Unity Hub.
2. Klik pada "New Project".
3. Pilih template "Universal 3D" dan beri nama proyek Anda, misalnya `GameVR`.
4. Klik "Create".

## Langkah 2: Install Meta SDK

1. menu `Window` > `Package Manager`.
2. Pilih `Meta XR All-In-One SDK` > `Install`.
3. Klik `Install`.
![Install Meta SDK](image1.png)

## Langkah 3: Menambahkan Skrip

1. Klik kanan pada folder `Assets` dan pilih `Create > C# Script`.
2. Beri nama skrip Anda, misalnya `PlayerController`.
3. Buka skrip di Visual Studio dan tambahkan kode berikut:

   ```csharp
   using UnityEngine;

   public class PlayerController : MonoBehaviour
   {
       public float speed = 5f;

       void Update()
       {
           float moveHorizontal = Input.GetAxis("Horizontal");
           float moveVertical = Input.GetAxis("Vertical");

           Vector2 movement = new Vector2(moveHorizontal, moveVertical);
           transform.Translate(movement * speed * Time.deltaTime);
       }
   }