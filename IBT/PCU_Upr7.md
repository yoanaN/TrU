1) Да се начертае алгоритъма за работа на тригера
2) Да се напише необходимия сорс код за проектиране на тригера


### 1.Стартиране:
Начало на алгоритъма.
### 2.Приемане на входни данни:
Приема входни данни D (Data), CLK (Clock) и SET (Async Set).
### 3.Проверка на SET сигнала:
Проверка дали SET е активен.
Ако SET е активен, преминава към стъпка 6.
### 4.Проверка на фронта на тактовия сигнал:
Проверка за възникване на положителен фронт (rising edge) на тактовия сигнал CLK.
Ако няма положителен фронт, продължава с проверка на SET.
### 5.Пренасяне на D към Q:
Пренася стойността на D към изхода Q.
### 6.Установяване на Q чрез SET:
Установява стойността на Q в желаната стойност при активиран SET сигнал.
### 7.Край:
Край на алгоритъма.

## Код VHDL
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity DFF_with_async_set is
    Port ( D : in STD_LOGIC;
           CLK : in STD_LOGIC;
           SET : in STD_LOGIC;
           Q : out STD_LOGIC);
end DFF_with_async_set;

architecture Behavioral of DFF_with_async_set is
begin
    process (CLK, SET)
    begin
        if SET = '1' then
            -- Асинхронно установяване
            Q <= '1';
        elsif rising_edge(CLK) then
            -- Обикновено пренасяне на стойността на D
            Q <= D;
        end if;
    end process;
end Behavioral;
