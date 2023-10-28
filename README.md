- 👋 Hi, I’m @OscarLeonardoFD
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
OscarLeonardoFD/OscarLeonardoFD is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
create database tarea_3_1;
use tarea_3_1;
create table persona(
peso int,
estado varchar(20));

delimiter $
create procedure persona1(in _peso int, out _estado varchar(20))
begin
set @estado=0;
select count(*)into @donante from persona where peso=_peso;
if @estado >=50 then

set _estado='admitido';
else 
set _estado='no admitido';
set _estado=@estado;
insert into persona(peso,estado) values(_peso,@estado);
end if;


end
$
