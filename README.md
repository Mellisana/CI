Перед вами код сервисного класса:

```package ru.netology.statistic;

public class StatisticsService {
    public long findMax(long[] incomes) {
        long currentMax = incomes[0];
        for (long income : incomes) {
            if (currentMax < income) {
                currentMax = income;
            }
        }
        return currentMax;
    }
}```
И код тест-класса, который его тестирует:

package ru.netology.statistic;

import org.junit.jupiter.api.Test;

import org.junit.jupiter.api.Assertions;

public class StatisticsServiceTest {

  @Test
  void findMax() {
    StatisticsService service = new StatisticsService();

    long[] incomesInBillions = {12, 5, 8, 4, 5, 3, 8, 6, 11, 11, 12};
    long expected = 12;

    long actual = service.findMax(incomesInBillions);

    Assertions.assertEquals(expected, actual);
  }
}
Ваша задача состоит в том, чтобы:

создать Maven-проект и поместить в него эти два класса;
запустить mvn clean test и убедиться, что тесты проходят;
создать публичный репозиторий и запушить в него проект;
настроить CI на основе GitHub Actions, после чего не забыть сделать git pull;
добавить в проект JaCoCo и настроить его в режиме обрушения сборки по недостаточному покрытию, а именно 100% покрытие по счётчику BRANCH;
запустить mvn clean verify и убедиться, что сборка упадёт из-за недостаточного покрытия;
проанализировать сгенерированный отчёт по покрытию, дописать недостающие тесты для полного покрытия, сам сервисный класс трогать нельзя;
сделать коммит и пуш, убедиться, что сборка на ГитХабе проходит.
Правила приёма работы
Прикреплена одна ссылка на публичный репозиторий с решением задачи.
