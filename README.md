# La Redonda — Fútbol 5 Manager

## Deploy en Vercel

### 1. Subir a GitHub
1. Creá un repositorio nuevo en github.com (puede ser privado)
2. Subí los dos archivos: `index.html` y `vercel.json`

### 2. Deploy en Vercel
1. Entrá a vercel.com e iniciá sesión con GitHub
2. Click en "Add New Project"
3. Seleccioná el repositorio
4. Click en "Deploy" (sin cambiar nada)
5. En ~30 segundos tenés tu URL: `la-redonda.vercel.app`

### 3. Crear el usuario Admin
Una vez que la app esté online:
1. Abrí la URL de Vercel
2. En Supabase → Authentication → Users → "Invite user" con tu mail
3. O usá el SQL Editor de Supabase:
```sql
-- Después de crear el usuario desde la app, hacelo admin:
UPDATE profiles SET role = 'admin' WHERE email = 'tu@mail.com';
```

### Primer acceso
1. Usá la pantalla de login para registrarte
2. Luego desde Supabase Table Editor, en la tabla `profiles`, 
   cambiá tu `role` a `admin`
3. ¡Listo! Recargá la app y ya sos admin.

### Crear jugadores
1. Como admin, andá a Equipos → creá tus equipos con jugadores
2. En Usuarios → "Crear usuario" → cargás mail + contraseña + vinculás al jugador
3. El jugador entra con esas credenciales y solo ve su equipo
