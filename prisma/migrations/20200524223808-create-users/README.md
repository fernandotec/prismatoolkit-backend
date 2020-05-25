# Migration `20200524223808-create-users`

This migration has been generated by Fernando Rodrigues at 5/24/2020, 10:38:08 PM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
CREATE TABLE "public"."User" (
"email" text  NOT NULL ,"id" SERIAL,"name" text   ,
    PRIMARY KEY ("id"))

CREATE UNIQUE INDEX "User.email" ON "public"."User"("email")
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration ..20200524223808-create-users
--- datamodel.dml
+++ datamodel.dml
@@ -1,0 +1,13 @@
+datasource db {
+  provider = "postgresql"
+  url      = env("DATABASE_URL")
+}
+
+generator client {
+  provider = "prisma-client-js"
+}
+model User {
+  id      Int      @default(autoincrement()) @id
+  email   String   @unique
+  name    String?
+}
```

