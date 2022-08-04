# LAB
Interfaz de usuario
classdef app2 < matlab.apps.AppBase

    % Properties that correspond to app components
    properties (Access = public)
        UIFigure                        matlab.ui.Figure
        TabGroup                        matlab.ui.container.TabGroup
        IngresodedatosTab               matlab.ui.container.Tab
        Image                           matlab.ui.control.Image
        IngresarButton                  matlab.ui.control.Button
        button                          matlab.ui.control.Button
        tabla                           matlab.ui.control.Table
        cantidad                        matlab.ui.control.NumericEditField
        CantidadEditFieldLabel          matlab.ui.control.Label
        potencia                        matlab.ui.control.NumericEditField
        PotenciaEditFieldLabel          matlab.ui.control.Label
        barra1                          matlab.ui.control.DropDown
        ElectrodomesticosDropDownLabel  matlab.ui.control.Label
        AnalisisTab                     matlab.ui.container.Tab
        Image_2                         matlab.ui.control.Image
        barra2                          matlab.ui.control.DropDown
        ElecctrodomesticosDropDownLabel  matlab.ui.control.Label
        axes2                           matlab.ui.control.UIAxes
        FacturacionTab                  matlab.ui.container.Tab
        CalcularButton                  matlab.ui.control.Button
        tabla3                          matlab.ui.control.Table
        Image_3                         matlab.ui.control.Image
    end

    % Callbacks that handle component events
    methods (Access = private)

        % Button pushed function: button
        function buttonPushed(app, event)
            t=readtable("data.xlsx")
            app.tabla.Data=t



            

        end

        % Button pushed function: IngresarButton
        function IngresarButtonPushed(app, event)
            global Refrigerador
            global Microondas
            global Celulares
            global Telefono_Convencional
            global Laptops
            global Televisores
            global Lavadora
            global Aires_Acondicionados
            global Luminarias 
            global Ventiladores
            global Secadora 

           

            
            if strcmp(app.barra1.Value,"Refrigerador")==1
                Refrigerador=[app.cantidad.Value,app.potencia.Value]
                
            end

            if strcmp(app.barra1.Value,"Microondas")==1
                Microondas=[app.cantidad.Value,app.potencia.Value]
            end
            if strcmp(app.barra1.Value,"Celulares")==1
                Celulares=[app.cantidad.Value,app.potencia.Value]
            end
            if strcmp(app.barra1.Value,"Telefono Convencional")==1
                Telefono_Convencional=[app.cantidad.Value,app.potencia.Value]
            end
            if strcmp(app.barra1.Value,"Laptops")==1
                Laptops=[app.cantidad.Value,app.potencia.Value]
            
            end
            if strcmp(app.barra1.Value,"Televisores")==1
                Televisores=[app.cantidad.Value,app.potencia.Value]
            end
            if strcmp(app.barra1.Value,"Lavadora")==1
                Lavadora=[app.cantidad.Value,app.potencia.Value]
            end
            if strcmp(app.barra1.Value,"Aires Acondicionados")==1
                Aires_Acondicionados=[app.cantidad.Value,app.potencia.Value]
            end
            if strcmp(app.barra1.Value,"Luminarias")==1
                Luminarias=[app.cantidad.Value,app.potencia.Value]
            end
            if strcmp(app.barra1.Value,"Ventiladores")==1
                Ventiladores=[app.cantidad.Value,app.potencia.Value]
            end
            if strcmp(app.barra1.Value,"Secadora")==1
                Secadora=[app.cantidad.Value,app.potencia.Value]
            end

        end

        % Value changed function: barra2
        function barra2ValueChanged(app, event)
            value = app.barra2.Value;
            global Refrigerador 
            global Microondas
            global Celulares
            global Telefono_Convencional
            global Laptops
            global Televisores
            global Lavadora
            global Aires_Acondicionados
            global Luminarias 
            global Ventiladores
            global Secadora
            global RefrigeradorE
            global MicroondasE
            global CelularesE
            global Telefono_ConvencionalE
            global LaptopsE
            global TelevisoresE
            global LavadoraE
            global Aires_AcondicionadosE
            global LuminariasE 
            global VentiladoresE
            global SecadoraE
           

            r=app.tabla.Data
            x=[0:23]
            if strcmp(value,"Refrigerador")==1
                y=Refrigerador(1)*Refrigerador(2)*table2array(r(1,2:25))
                RefrigeradorE=Refrigerador(1)*Refrigerador(2)*sum(table2array(r(1,2:25)))
                plot(app.axes2,x,y)
            end
            if strcmp(value,"Microondas")==1
                
                y= Microondas(1)*Microondas(2)*table2array(r(2,2:25))
                MicroondasE=Microondas(1)*Microondas(2)*sum(table2array(r(2,2:25)))
                plot(app.axes2,x,y)
            end
                
            if strcmp(value,"Celulares")==1
                
                y=Celulares(1)*Celulares(2)*table2array(r(3,2:25))
                CelularesE=Celulares(1)*Celulares(2)*sum(table2array(r(3,2:25)))
                plot(app.axes2,x,y)
            end
                
            if strcmp(value,"Telefono Convencional")==1
                
                y=Telefono_Convencional(1)*Telefono_Convencional(2)*table2array(r(4,2:25))
                Telefono_ConvencionalE=Telefono_Convencional(1)*Telefono_Convencional(2)*sum(table2array(r(4,2:25)))
                plot(app.axes2,x,y)
            end
            if strcmp(value,"Laptops")==1
                
                y=Laptops(1)*Laptops(2)*table2array(r(5,2:25))
                LaptopsE=Laptops(1)*Laptops(2)*sum(table2array(r(5,2:25)))
                plot(app.axes2,x,y)
            end
                
            if strcmp(value,"Televisores")==1
                
                y=Televisores(1)*Televisores(2)*table2array(r(6,2:25))
                TelevisoresE=Televisores(1)*Televisores(2)*sum(table2array(r(6,2:25)))
                plot(app.axes2,x,y)
            end
                
            if strcmp(value,"Lavadora")==1
                
                y=Lavadora(1)*Lavadora(2)*table2array(r(7,2:25))
                LavadoraE=Lavadora(1)*Lavadora(2)*sum(table2array(r(7,2:25)))
                plot(app.axes2,x,y)
            end
                
            if strcmp(value,"Aires Acondicionados")==1
                
                y=Aires_Acondicionados(1)*Aires_Acondicionados(2)*table2array(r(8,2:25))
                Aires_AcondicionadosE=Aires_Acondicionados(1)*Aires_Acondicionados(2)*sum(table2array(r(8,2:25)))
                plot(app.axes2,x,y)
            end
                
            if strcmp(value,"Luminarias")==1
               
                y=Luminarias(1)*Luminarias(2)*table2array(r(9,2:25))
                LuminariasE=Luminarias(1)*Luminarias(2)*sum(table2array(r(9,2:25)))
                plot(app.axes2,x,y)
            end
               
            if strcmp(value,"Ventiladores")==1
                
                y=Ventiladores(1)*Ventiladores(2)*table2array(r(10,2:25))
                VentiladoresE=Ventiladores(1)*Ventiladores(2)*sum(table2array(r(10,2:25)))
                plot(app.axes2,x,y)
            end
               
            if strcmp(value,"Secadora")==1
               
                y=Secadora(1)*Secadora(2)*table2array(r(11,2:25))
                SecadoraE=Secadora(1)*Secadora(2)*sum(table2array(r(11,2:25)))
                plot(app.axes2,x,y)
            end
 
            global Energia
            Energia=sum([RefrigeradorE,MicroondasE,CelularesE,Telefono_ConvencionalE,LaptopsE,TelevisoresE,LavadoraE,Aires_AcondicionadosE,LuminariasE,VentiladoresE,SecadoraE])
           
            

            
            
        end

        % Button pushed function: CalcularButton
        function CalcularButtonPushed(app, event)
            global Energia
            global tasa
            tasa=0.092
            global Costo
            Costo=Energia*tasa
            t=[Energia,tasa,Costo]
            app.tabla3.Data=t
        end
    end

    % Component initialization
    methods (Access = private)

        % Create UIFigure and components
        function createComponents(app)

            % Get the file path for locating images
            pathToMLAPP = fileparts(mfilename('fullpath'));

            % Create UIFigure and hide until all components are created
            app.UIFigure = uifigure('Visible', 'off');
            app.UIFigure.Position = [100 100 640 554];
            app.UIFigure.Name = 'MATLAB App';

            % Create TabGroup
            app.TabGroup = uitabgroup(app.UIFigure);
            app.TabGroup.Position = [2 0 633 553];

            % Create IngresodedatosTab
            app.IngresodedatosTab = uitab(app.TabGroup);
            app.IngresodedatosTab.Title = 'Ingreso de datos ';

            % Create ElectrodomesticosDropDownLabel
            app.ElectrodomesticosDropDownLabel = uilabel(app.IngresodedatosTab);
            app.ElectrodomesticosDropDownLabel.HorizontalAlignment = 'right';
            app.ElectrodomesticosDropDownLabel.Position = [26 440 107 22];
            app.ElectrodomesticosDropDownLabel.Text = 'Electrodomesticos ';

            % Create barra1
            app.barra1 = uidropdown(app.IngresodedatosTab);
            app.barra1.Items = {'Refrigerador', 'Microondas', 'Celulares', 'Telefono Convencional', 'Laptops', 'Televisores', 'Lavadora', 'Aires Acondicionados', 'Luminarias', 'Ventiladores', 'Secadora'};
            app.barra1.Position = [148 421 120 59];
            app.barra1.Value = 'Refrigerador';

            % Create PotenciaEditFieldLabel
            app.PotenciaEditFieldLabel = uilabel(app.IngresodedatosTab);
            app.PotenciaEditFieldLabel.HorizontalAlignment = 'right';
            app.PotenciaEditFieldLabel.Position = [28 365 55 22];
            app.PotenciaEditFieldLabel.Text = 'Potencia';

            % Create potencia
            app.potencia = uieditfield(app.IngresodedatosTab, 'numeric');
            app.potencia.Position = [98 355 170 41];

            % Create CantidadEditFieldLabel
            app.CantidadEditFieldLabel = uilabel(app.IngresodedatosTab);
            app.CantidadEditFieldLabel.HorizontalAlignment = 'right';
            app.CantidadEditFieldLabel.Position = [26 309 55 22];
            app.CantidadEditFieldLabel.Text = 'Cantidad';

            % Create cantidad
            app.cantidad = uieditfield(app.IngresodedatosTab, 'numeric');
            app.cantidad.Position = [96 299 170 41];

            % Create tabla
            app.tabla = uitable(app.IngresodedatosTab);
            app.tabla.ColumnName = {'Electrodomesticos'; '00:00'; '01:00'; '02:00'; '03:00'; '04:00'; '05:00'; '06:00'; '07:00'; '08:00'; '09:00'; '10:00'; '11:00'; '12:00'; '13:00'; '14:00'; '15:00'; '16:00'; '17:00'; '18:00'; '19:00'; '20:00'; '21:00'; '22:00'; '23:00'};
            app.tabla.RowName = {'1'; '2'; '3'; '4'; '5'; '6'; '7'; '8'; '9'; '10'; '11'};
            app.tabla.ColumnEditable = true;
            app.tabla.Position = [113 105 441 161];

            % Create button
            app.button = uibutton(app.IngresodedatosTab, 'push');
            app.button.ButtonPushedFcn = createCallbackFcn(app, @buttonPushed, true);
            app.button.Position = [196 30 246 60];
            app.button.Text = 'Datos';

            % Create IngresarButton
            app.IngresarButton = uibutton(app.IngresodedatosTab, 'push');
            app.IngresarButton.ButtonPushedFcn = createCallbackFcn(app, @IngresarButtonPushed, true);
            app.IngresarButton.Position = [416 297 96 34];
            app.IngresarButton.Text = 'Ingresar';

            % Create Image
            app.Image = uiimage(app.IngresodedatosTab);
            app.Image.Position = [510 18 101 61];
            app.Image.ImageSource = fullfile(pathToMLAPP, 'logo espol.jpg');

            % Create AnalisisTab
            app.AnalisisTab = uitab(app.TabGroup);
            app.AnalisisTab.Title = 'Analisis';

            % Create axes2
            app.axes2 = uiaxes(app.AnalisisTab);
            title(app.axes2, 'Potencia vs Tiempo')
            xlabel(app.axes2, 'Horas')
            ylabel(app.axes2, 'Potencia W')
            zlabel(app.axes2, 'Z')
            app.axes2.Position = [82 159 430 228];

            % Create ElecctrodomesticosDropDownLabel
            app.ElecctrodomesticosDropDownLabel = uilabel(app.AnalisisTab);
            app.ElecctrodomesticosDropDownLabel.HorizontalAlignment = 'right';
            app.ElecctrodomesticosDropDownLabel.Position = [11 438 110 22];
            app.ElecctrodomesticosDropDownLabel.Text = 'Elecctrodomesticos';

            % Create barra2
            app.barra2 = uidropdown(app.AnalisisTab);
            app.barra2.Items = {'Refrigerador ', 'Microondas', 'Celulares', 'Telefono Convencional', 'Laptops', 'Televisores', 'Lavadora', 'Aires Acondicionados', 'Luminarias ', 'Ventiladores', 'Secadora '};
            app.barra2.ValueChangedFcn = createCallbackFcn(app, @barra2ValueChanged, true);
            app.barra2.Position = [136 422 159 53];
            app.barra2.Value = 'Refrigerador ';

            % Create Image_2
            app.Image_2 = uiimage(app.AnalisisTab);
            app.Image_2.Position = [510 18 101 61];
            app.Image_2.ImageSource = fullfile(pathToMLAPP, 'logo espol.jpg');

            % Create FacturacionTab
            app.FacturacionTab = uitab(app.TabGroup);
            app.FacturacionTab.Title = 'Facturacion ';

            % Create Image_3
            app.Image_3 = uiimage(app.FacturacionTab);
            app.Image_3.Position = [510 18 101 61];
            app.Image_3.ImageSource = fullfile(pathToMLAPP, 'logo espol.jpg');

            % Create tabla3
            app.tabla3 = uitable(app.FacturacionTab);
            app.tabla3.ColumnName = {'Consumo'; 'Tasa'; 'Costo'};
            app.tabla3.RowName = {};
            app.tabla3.Position = [162 260 350 110];

            % Create CalcularButton
            app.CalcularButton = uibutton(app.FacturacionTab, 'push');
            app.CalcularButton.ButtonPushedFcn = createCallbackFcn(app, @CalcularButtonPushed, true);
            app.CalcularButton.Position = [294 182 108 43];
            app.CalcularButton.Text = 'Calcular';

            % Show the figure after all components are created
            app.UIFigure.Visible = 'on';
        end
    end

    % App creation and deletion
    methods (Access = public)

        % Construct app
        function app = app2

            % Create UIFigure and components
            createComponents(app)

            % Register the app with App Designer
            registerApp(app, app.UIFigure)

            if nargout == 0
                clear app
            end
        end

        % Code that executes before app deletion
        function delete(app)

            % Delete UIFigure when app is deleted
            delete(app.UIFigure)
        end
    end
end
