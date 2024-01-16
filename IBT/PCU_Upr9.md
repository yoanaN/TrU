

В този пример, архитектурата "Behavioral" включва процес, чувствителен към промените във входовете A и B.
В процеса има просто уравнение, което присвоява резултата от операцията И (AND) между A и B на изхода C.
## Код

library IEEE;
use IEEE.std_logic_1164.all;

entity Fub1 is
    port (
        A : in STD_LOGIC;
        B : in STD_LOGIC;
        C : out STD_LOGIC
    );
end Fub1;

architecture Behavioral of Fub1 is
begin
    process (A, B)
    begin
        -- Уравнение за порта И (AND)
        C <= A AND B;
    end process;
end Behavioral;
