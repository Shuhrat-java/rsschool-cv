
1. Shuhrat Akramov
2. shuh100@gmail.com, qolu@mail.ru
3. Goal - to be self employed. Create great projects.
4. Skills. C#, Java/Android, C++, Sql Server, Google Cloud Rest Apis,...
5.
<code>

        public static string Encrypt(string plainText, byte[] key, byte[] iv)
        {
            try
            {
                RijndaelManaged aes = new RijndaelManaged
                {
                    KeySize = 256,
                    BlockSize = 128,
                    Padding = PaddingMode.PKCS7,
                    Mode = CipherMode.CBC,
                    Key=key,
                    IV=iv
                };  

                ICryptoTransform AESEncrypt = aes.CreateEncryptor(aes.Key, aes.IV);
                byte[] buffer = encoding.GetBytes(plainText);

                string encryptedText = Convert.ToBase64String(AESEncrypt.TransformFinalBlock(buffer, 0, buffer.Length));

                return encryptedText;
            }
            catch (Exception e)
            {
                throw new Exception("Error encrypting: " + e.Message);
            }
        }

        public static string Decrypt(string plainText, byte[] key, byte[] iv)
        {
            try
            {
                RijndaelManaged aes = new RijndaelManaged
                {
                    KeySize = 256,
                    BlockSize = 128,
                    Padding = PaddingMode.PKCS7,
                    Mode = CipherMode.CBC,
                    Key =  key,
                    IV =  iv
                };

                // Base 64 decode
                byte[] base64Decoded = Convert.FromBase64String(plainText);

                ICryptoTransform AESDecrypt = aes.CreateDecryptor(aes.Key, aes.IV);
                byte[] buffer = base64Decoded;

                return encoding.GetString(AESDecrypt.TransformFinalBlock(buffer, 0, buffer.Length));
            }
            catch (Exception e)
            {
                throw new Exception("Error decrypting: " + e.Message);
            }
        }
        
</code>
6. Experience. Android development, Server based C# console app, Sql server database design and management
7. Education. Tashkent university of information technologies 
8. English. Upper intermediate
