```mermaid
graph TD
subgraph "Главный поток: Возмещение расходов на проезд"
A["start: Вы хотите получить возмещение расходов на проезд?"] -->|Да| B{"Вы оформляете для себя или как представитель?"};
A -->|Нет| C["final: Хорошо, диалог завершен."];
B -->|"Для себя"| D["Переход к потоку 'Для себя'"];
B -->|"Представитель"| E["Переход к потоку 'Представитель'"];
end

    subgraph "Поток 2: Оформление для себ[report-gosudarstvennaya-registratsiya-rastorzheniya-braka-v-mfts-4d6c4926-198a-4ef2-9bbd-93c29f78be43.md](report-gosudarstvennaya-registratsiya-rastorzheniya-braka-v-mfts-4d6c4926-198a-4ef2-9bbd-93c29f78be43.md)я"
        D --> F{"Относитесь ли вы к льготной категории?"};
        F -->|Да| G{"Обращались за компенсацией в последние 2 года?"};
        F -->|Нет| H_Reject["final: Отказ - нет льготного статуса"];
        G -->|Да| H_Reject;
        G -->|Нет| I{"Поездка связана с лечением в санатории?"};
        I -->|Да| J_Self_Med["final: Список документов с мед. заключением"];
        I -->|Нет| K_Self_Base["final: Базовый список документов"];
    end

    subgraph "Поток 3: Оформление через представителя"
        E --> L{"Входит ли льготник в льготную категорию?"};
        L -->|Да| M{"Обращался ли заявитель за компенсацией в последние 2 года?"};
        L -->|Нет| N_Reject["final: Отказ - нет льготного статуса"];
        M -->|Да| N_Reject;
        M -->|Нет| O{"Поездка льготника связана с лечением в санатории?"};
        O -->|Да| P_Rep_Med["final: Список документов для представителя с мед. заключением"];
        O -->|Нет| Q_Rep_Base["final: Базовый список документов для представителя"];
    end

    %% Стилизация для наглядности
    style A fill:#c9f,stroke:#333,stroke-width:2px
    style C fill:#f9f,stroke:#333,stroke-width:2px
    style H_Reject fill:#f99,stroke:#333,stroke-width:2px
    style N_Reject fill:#f99,stroke:#333,stroke-width:2px
    style J_Self_Med fill:#9cf,stroke:#333,stroke-width:2px
    style K_Self_Base fill:#9cf,stroke:#333,stroke-width:2px
    style P_Rep_Med fill:#9cf,stroke:#333,stroke-width:2px
    style Q_Rep_Base fill:#9cf,stroke:#333,stroke-width:2px
```
