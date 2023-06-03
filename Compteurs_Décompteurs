library ieee;
use ieee.std_logic_1164.all;
entity counter is
    port(
        clk     : in std_logic;
        reset   : in std_logic;
        load    : in std_logic;
        sens    : in std_logic;
        data_in : in std_logic_vector(3 downto 0);
        q       : out std_logic_vector(3 downto 0)
    );
end entity counter;

architecture behavioral of counter is
    signal count : std_logic_vector(3 downto 0);
begin
    process(clk, reset)
    begin
        if reset = '1' then
            count <= (others => '0'); -- Remise à zéro asynchrone
        elsif rising_edge(clk) then
            if load = '1' then
                count <= data_in; -- Rechargement synchrone
            elsif sens = '1' then
                count <= count + 1; -- Incrémentation synchrone
            else
                count <= count - 1; -- Décrémentation synchrone
            end if;
        end if;
    end process;
    q <= count;
end architecture behavioral;
