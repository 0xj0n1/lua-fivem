--------------------------
-- > local & print < -- 
--------------------------

local Number5   = 5                         -- Variable mit Nummer
local Hello     = "Hallo"                   -- Variable mit Text

print("Text immer in Anführungszeichen")    -- Konsolen ausgabe mit Text
print(5)                                    -- Zahlen müssen nicht in Anführungszeichen     / Konsolen ausgabe mit Nummer

print(Number5)                              -- Variablen Ausgabe
print(Hello)                                -- Variablen Ausgabe





--------------------------
-- >    Operatoren    < --
--------------------------

if        Wert1 == Wert2    then        -- Wert1 entspricht GENAU Wert2
elseif    Wert1 ~= Wert2    then        -- Wert1 entspricht NICHT Wert2
elseif    Wert1 < Wert2     then        -- Wert1 ist kleiner als Wert2
elseif    Wert1 > Wert2     then        -- Wert1 ist größer als Wert2
elseif    Wert1 <= Wert2    then        -- Wert1 ist kleiner ODER gleich Wert2
elseif    Wert1 >= Wert2    then        -- Wert1 ist größer ODER gleich Wert2
end




--------------------------
-- > If, elseif, else < --
--------------------------

local Status1 = true
local Status2 = false

if Status1 == true then                 -- Ist Status1 true, dann
    -- Do Stuff                         -- Mach das
elseif Status2 then                     -- Ist Status2 true, dann        
    -- Do Stuff                         -- Mach das
else                                    -- Wenn das alles nichts eintrifft
    -- Do Stuff                         -- Mach das
end                                     -- Ende der If abfrage





--------------------------
-- >  while schleife  < --
--------------------------

--Beispiel 1
Citizen.CreateThread(function()  
    while true do                           -- Während die bedingung true ist beginnt die schleife der wert "true" heißt gleich dauerhaft
        Citizen.Wait(1)                     -- Warte 1ms, weil ansonsten zu kommts zum Crash
                                            -- Hier kommt das rein, was du ausführen willst
    end                                     -- Ende von der while schleife
end)                                        -- Ende vom Thread

--Beispiel 2
local Status1 = true
Citizen.CreateThread(function()  
    while Status1 do                        -- Während Status1 true ist beginnt die schleife, bis Status1 nicht mehr true ist
        Citizen.Wait(1)                     -- Warte 1ms, weil ansonsten zu kommts zum Crash
                                            -- Hier kommt das rein, was du ausführen willst
    end                                     -- Ende von der while schleife
end)                                        -- Ende vom Thread





--------------------------
-- >  Sämtliche Gets  < --
--------------------------

local ServerID  = GetPlayerServerId(PlayerId())
local PlayerID  = PlayerId()
local Ped       = GetPlayerPed(-1)              -- -1 ist immer der Spieler selbst

local VehicleIn = GetVehiclePedIsIn(PlayerPedId(), false) -- Gibt das Fahrzeug zurück, indem der Spieler gerade sitzt




--------------------------
-- >     Functions    < --
--------------------------

    ---- > Eine Function dient dazu innerhalb einer Datei sachen zu Triggern < ----

-- Erstellen einer function OHNE Parametern
function Name()

end

-- Erstellen einer function MIT Parametern
function Name(param1, param2, usw)

end

--Triggern eines function OHNE Parametern
Name()

--Triggern eines function MIT Parametern
Name(param1, param2, usw)



--Beispiel 1
function HelloWorld()
    print("Hello World")
end

HelloWorld()



--Beispiel 2
function addiere(zahl1, zahl2)
    print(zahl1 + zahl2)                                    --> Ausgabe: Die Summe von Zahl 1 & 2
    print(zahl1.." + "..zahl2.." = ".. zahl1 + zahl2 )      
end

addiere(5, 10)      --> Print Ausgabe "5 + 10 = 15" 



--Beispiel 3
function SagHallo(Name)
    print("Hallo "..Name) 
end

SagHallo("Synix")      --> Print Ausgabe "Hallo Synix" 





--------------------------
-- >       Events     < --
--------------------------

    ---- > Ein Event dient dazu zwischen Mehreren Dateien sachen zu Triggern < ----

--Erstellen eines Events OHNE Parametern
RegisterNetEvent('EventName')
AddEventHandler('EventName', function()

end)

--Erstellen eines Events MIT Parametern
RegisterNetEvent('EventName')
AddEventHandler('EventName', function(eventParam1, eventParam2, usw)

end)

--Triggern eines Events OHNE Parametern
TriggerEvent("EventName")                                                       -- Von Client-Side zu Client-Side // Von Server-Side zu Server-Side
TriggerServerEvent("EventName")                                                 -- Von Client-Side zu Server-Side 
TriggerClientEvent("EventName", targetPlayer)                                   -- Von Server-Side zu Client-Side       WICHTIG: targetPlayer ist die ServerID des Spielers, an den das Event gehen soll!!!

--Triggern eines Events MIT Parametern
TriggerEvent("EventName", eventParam1, eventParam2, usw)                            -- Von Client-Side zu Client-Side // Von Server-Side zu Server-Side
TriggerServerEvent("EventName", eventParam1, eventParam2, usw)                      -- Von Client-Side zu Server-Side 
TriggerClientEvent("EventName", targetPlayer, eventParam1, eventParam2, usw)        -- Von Server-Side zu Client-Side        CHTIG: targetPlayer ist die ServerID des Spielers, an den das Event gehen soll!!!
