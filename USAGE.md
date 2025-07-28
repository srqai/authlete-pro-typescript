<!-- Start SDK Example Usage [usage] -->
```typescript
import { AutheletePro } from "authelete-pro";

const autheletePro = new AutheletePro({
  apiKey: process.env["AUTHELETEPRO_API_KEY"] ?? "",
});

async function run() {
  const result = await autheletePro.pet.updatePet({
    id: 10,
    name: "doggie",
    category: {
      id: 1,
      name: "Dogs",
    },
    photoUrls: [
      "<value 1>",
    ],
  });

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->