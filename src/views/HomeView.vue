<template>
  <section>
    <div class="container py-5 text-black">
      <!--image and first paragraphs-->
      <description/>
      <!--Steps for buying on leasing-->
      <section class="text-start">
        <h1>
          <strong>Чекори за купување возило на лизинг:</strong>
        </h1>
        <ol>
          <steps-for-buying-car v-for="step in stepsForLeasing" :steps="step"/>
        </ol>
        <p>
          <strong class="ps-4">НАПОМЕНА: Пред превземање на возилото потребно е да обезбедите КАСКО ПОЛИСА.</strong>
        </p>
      </section>
      <!--Documentation for natural person-->
      <section>
        <documentation-for-natural-person :descForNaturalPerson="descForNatural"/>
      </section>
      <!--Documentation for LEGAL ENTITIES-->
      <section>
        <documentation-for-legal-entities :descForLegalEntities="descForLegal"/>
      </section>
      <!--WARNING-->
      <section class="text-danger text-start">
        <p>
          <i>* НАПОМЕНА: ДОКОЛКУ ПОДАТОЦИТЕ КОИ ГИ ОСТАВАТЕ ПРИ ПРЕД-ОДОБРУВАЊЕТО НЕ СЕ ТОЧНИ И ПРЕЦИЗНИ МОЖНО Е АПЛИКАЦИЈАТА ЗА ЛИЗИНГ ДА ВИ БИДЕ ОДБИЕНА ИЛИ ПРОЛОНГИРАНА ОД СТРАНА НА БАНКАТА И ПРИТОА ГО ГУБИТЕ ОСТАВЕНИОТ КАПАР.</i>
        </p>
      </section>
    </div>
  </section>
</template>


<script>
// @ is an alias to /src
import StepsForBuyingCar from "@/components/StepsForBuyingCar";
import Description from "@/components/Description";
import DocumentationForNaturalPerson from "@/components/DocumentationForNaturalPerson";
import DocumentationForLegalEntities from "@/components/DocumentationForLegalEntities";

export default {
  name: 'HomeView',
  components: {
    StepsForBuyingCar,
    Description,
    DocumentationForNaturalPerson,
    DocumentationForLegalEntities
  },
  data() {
    return {
      descForNatural: {
        heading1: '<h1><strong>Документација со барање за лизинг: ФИЗИЧКИ ЛИЦА</strong></h1>',
        paragraph1: '<p>Со пополнето барање за одобрување на лизинг, <strong>профактура на добавувачот</strong> и <strong>прифатена лизинг понуда</strong>, потребно е да се приложат и:</p>',
        li1: 'ПРОФАКТУРА',
        li2: '<li>БАРАЊЕ за одобрување на лизинг (<strong><a href="https://s-leasing.mk/content/%D0%91%D0%B0%D1%80%D0%B0%D1%9A%D0%B5%20%D0%B7%D0%B0%20%D0%BE%D0%B4%D0%BE%D0%B1%D1%80%D1%83%D0%B2%D0%B0%D1%9A%D0%B5%20%D0%BD%D0%B0%20%D0%BB%D0%B8%D0%B7%D0%B8%D0%BD%D0%B3-Fizicki%20Lica.pdf">превземи барање</a></strong>)</li>',
        li3: 'Копија од ЛИЧНА КАРТА',
        li4: 'ПОТВРДА од работодавецот за редовен работен однос',
        li5: '<li>Административна забрана од плата од работодавецот (<strong><a href="https://s-leasing.mk/content/%D0%90%D0%B4%D0%BC%D0%B8%D0%BD%D0%B8%D1%81%D1%82%D1%80%D0%B0%D1%82%D0%B8%D0%B2%D0%BD%D0%B0%20%D0%B7%D0%B0%D0%B1%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D0%B4%20%D0%BF%D0%BB%D0%B0%D1%82%D0%B0%20%D0%BE%D0%B4%20%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BE%D0%B4%D0%B0%D0%B2%D0%B5%D1%86%D0%BE%D1%82%20%D0%B2%D0%BE%20%D0%BA%D0%BE%D1%80%D0%B8%D1%81%D1%82%20%D0%BD%D0%B0%20%D0%A8%D0%9F%D0%90%D0%A0%D0%9A%D0%90%D0%A1%D0%95%20%D0%9B%D0%98%D0%97%D0%98%D0%9D%D0%93%20%D0%94%D0%9E%D0%9E%20%D0%A1%D0%BA%D0%BE%D0%BF%D1%98%D0%B5.pdf">превземи Административна забрана</a></strong>)</li>',
        li6: '<li>ИЗЈАВА за редовна отплата (<strong><a href="https://s-leasing.mk/content/%D0%98%D0%B7%D1%98%D0%B0%D0%B2%D0%B0%20%D0%B7%D0%B0%20%D1%80%D0%B5%D0%B4%D0%BE%D0%B2%D0%BD%D0%B0%20%D0%BE%D1%82%D0%BF%D0%BB%D0%B0%D1%82%D0%B0.pdf">превземи Изјава</a></strong>)</li>',
        li7: 'Годишна даночна пријава (доколку барателот остварува дополнителни приходи)',
        li8: 'Декларации за прием за бруто плата за последните 3 месеци',
        li9: '<li>СОГЛАСНОСТ за извадок од Македонско Кредитно Биро (<strong><a href="https://s-leasing.mk/content/%D0%A1%D0%BE%D0%B3%D0%BB%D0%B0%D1%81%D0%BD%D0%BE%D1%81%D1%82%20%D0%B7%D0%B0%20%D0%B8%D0%B7%D0%B2%D0%B0%D0%B4%D0%BE%D0%BA%20%D0%BE%D0%B4%20%D0%9C%D0%B0%D0%BA%D0%B5%D0%B4%D0%BE%D0%BD%D1%81%D0%BA%D0%BE%20%D0%9A%D1%80%D0%B5%D0%B4%D0%B8%D1%82%D0%BD%D0%BE%20%D0%91%D0%B8%D1%80%D0%BE.pdf">превземи согласност</a></strong>)</li>',
        paragraph2: '<p><strong>Документација треба да биде заверена со потпис и печат на овластеното лице!</strong></p>',
        paragraph3: '<p><strong>AUTOWELT</strong> го задржува правото да побара дополнителна документација за разгледување на барањата за одобрување на лизинг</p>',
      },
      descForLegal: {
        heading1: 'Документација со барање за лизинг: ПРАВНИ ЛИЦА',
        paragraph1: 'Со пополнето барање за одобрување на лизинг, профактура на добавувачот и прифатена лизинг понуда, потребно е да се приложат и:',
        li1: '<li>Барање за одобрување на лизинг (<strong><a target="_blank" href="https://s-leasing.mk/content/%D0%91%D0%B0%D1%80%D0%B0%D1%9A%D0%B5%20%D0%B7%D0%B0%20%D0%BE%D0%B4%D0%BE%D0%B1%D1%80%D1%83%D0%B2%D0%B0%D1%9A%D0%B5%20%D0%BD%D0%B0%20%D0%BB%D0%B8%D0%B7%D0%B8%D0%BD%D0%B3_Pravni%20Lica-11.01.2022.pdf">превземи барање</a></strong>)</li>',
        li2: 'Копија од тековна состојба, не постара од 6 недели',
        li3: 'Завршна сметка (биланс на состојба и биланс на успех за последните две фискални години)',
        li4: 'Аналитички заклучни листови кон завршните сметки за последните две години',
        li5: 'Аналитички заклучен лист за тековната година со последен датум на книжење',
        li6: '<li>Согласност за извадок од Македонско Кредитно Биро (<strong><a target="_blank" href="https://s-leasing.mk/content/%D0%A1%D0%BE%D0%B3%D0%BB%D0%B0%D1%81%D0%BD%D0%BE%D1%81%D1%82%20%D0%B7%D0%B0%20%D0%B8%D0%B7%D0%B2%D0%B0%D0%B4%D0%BE%D0%BA%20%D0%BE%D0%B4%20%D0%9C%D0%B0%D0%BA%D0%B5%D0%B4%D0%BE%D0%BD%D1%81%D0%BA%D0%BE%20%D0%9A%D1%80%D0%B5%D0%B4%D0%B8%D1%82%D0%BD%D0%BE%20%D0%91%D0%B8%D1%80%D0%BE.pdf">превземи согласност</a></strong>)</li>',
        li7: '<li>Изјава за вистински сопственик (<strong><a target="_blank" href="https://s-leasing.mk/content/Izjava-za-vistinski-sopstvenik.pdf">превземи согласност</a></strong>)</li>',
        paragraph2: 'Документација треба да биде заверена со потпис и печат на овластеното лице!',
        paragraph3: '<p><strong>AUTOWELT</strong> го задржува правото да побара дополнителна документација за разгледување на барањата за одобрување на лизинг.</p>'
      },
      stepsForLeasing: [
        {
          stepName: 'ИЗБЕРЕТЕ ГО ВОЗИЛОТО',
          description: 'Најпрво го избирате возилото кое сакате да го купите и добивате понуда за истото. Според изборот и понудата се подготвуваат потребните документи.'
        },
        {
          stepName: 'НАШИТЕ ВРАБОТЕНИ ЌЕ ВИ ГИ ПОБАРААТ ПОТРЕБНИТЕ ПОДАТОЦИ',
          description: 'Ги оставате сите потребни податоци на нашите вработени за да ја подготват целокупната документација која е потребна за аплицирање за лизингот.'
        },
        {
          stepName: 'ПРЕДОДОБРУВАЊЕ',
          description: 'Според податоците се преминува на фазата за пред-одобрување која ги елиминира или намалува можностите да бидете одбиени. Затоа е потребно податоците кои ќе ги оставите да бидат точни и прецизни.\n' +
              '  Лизинг копманијата ја разгледаува вашата апликација и дололку се е во ред ќе Ви го одобрат лизингот и ќе ве известат за тоа. Дополнително ќе ви ги кажат понатамошните чекори.'
        },
        {
          stepName: 'КАПАР',
          description: 'Доколку помине постапката на пред-одобрување потребно е да оставите капар за избраното возило за да Ви биде резервирано се до конечно одобрувањето од банката.'
        },
        {
          stepName: 'ПРЕЗЕМАЊЕ НА ВОЗИЛОТО',
          description: 'Откако ќе се завршите целата процедура и лизингот ќе биде одобрен се договара датумот за превземање на возилото.'
        }
      ]
    }
  }
}
</script>