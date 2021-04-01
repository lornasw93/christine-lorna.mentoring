# How-To

## Creating a new Angular Project

**1. cd your chosen repo directory**
```
cd C:\Users\lornn\source\repos\lornasw93\mentoring\christine
```

**2. Create new project (with routing enabled and styling set)**
```
ng n project-name --routing=true --style=less
```

**3. Basic pages added (new components)**
```
cd project-name/src/app
ng g c home
ng g c about
ng g c contact
```

**4. New shared folder with navbar and footer components**
```
mkdir shared
cd shared
ng g c navbar, footer
```

**5. Run project (on port 4200)**
```
ng serve --o
```

## Installing Bootstrap
