# Цель
Выполнить исследование мобильного приложения, дать рекомендации по внедрению набора акционных предложений в зависимости от полученных результатов, разработать функцию Retention для автоматизированного подсчета и визуализации. Разработать рекомендации по метрикам для оценки игрового события в двух разрезах: обычное/усложненная механика.

# Задачи
1) Пронализировала исходные данные.
2) Создала функцию для расчета Retention с отрисовкой графика.
3) Провела анализ контрольных групп в имеющемся A/B тесте по наборам предложений для пользователей.
4) Проверила статистическую значимость отличий в метриках ARPU, ARPPU, CR с помощью T-test Стьюдента, T-tеst Уэлча и Chi-squared test.
5) Разработала рекомендации по развитию и использованию метрик.

# Стек проекта
Python (pandas, numpy, matplotlib, scipy.stats, pingouin, seaborn).
Результат работы представлен в итоговом файле: **Research.ipynb**

# Результат

1) Функция расчета Retention работает корректно, отрисовывает график и выполняет поставленную задачу. Функция имеет документацию с описанием работы.
![image](https://github.com/octantus/Mobile-game-research/assets/65022781/643b0a41-18cd-4fab-ac1a-d967585c28dd)
2) Я провела исследование метрик ARPU, ARPPU и CR в контрольной и тестовой группе. Тесты показали, что статистически значимых различий в ARPU и ARPPU не наблюдается. При этом, статистические различия CR в контрольной и тестовой группе являются значимыми. В тестовой группе конверсия статистически значимо ниже, чем в контрольной группе.
3) Исходя из исследования самих данных видим, что пользователи, которые платят существенно много, находятся только в контрольной группе. В тестовой же группе платежи более устойчивые, без каких-либо скачков. Здесь можно задуматься о том, что, возможно, изначально проведенный A/B-тест наборов акционных предложений был проведен некорректно. Однако, тест всё же был проведен, поэтому также можно считать, что большие платежи в контрольной группе не являются аномалиями.
Узнать, какую цель преследовала компания, планируя данный эксперимент и в чем суть акционных предложений, можно узнать только у самой компании. 
4) На основе имеющихся данных, предложила два варианта развития событий:
- Если тестирование было проведено корректно - набор акционных предложений в контрольной группе смотрится привлекательнее на данный момент. Оставляем.
- Если тестирование было проведено некорректно и в контрольной группе имеются аномалии - принимаем акционные предложения тестовой группы.
5) В рекомендациях по метрикам выделила наиболее важные, которые помогут оценить результат события в игре: **Retention rate, DAU/MAU, ASD, SR, CSAT и CPA**. При усложнении механики игры в событии, помимо стандартного набора метрик, стоит опираться на **Churn rate, Success rate per levels, Average count of attempts**. Присутствуют самодельные метрики, поэтому даны рекомендации по их подсчету.
