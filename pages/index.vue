<template>
  <section class="section">
    <div class="container">

      <div class="columns">
        <div class="column">
          <form action="">
            <div class="field">
              <label class="label">Наименование</label>
              <div class="control">
                <input class="input" type="text" placeholder="Наименование">
              </div>
            </div>
            <div class="field">
              <label class="label">Количество</label>
              <div class="field has-addons">
                <p class="control">
                  <input class="input" type="number" placeholder="Количество">
                </p>
                <p class="control">
                  <a class="button is-static">
                    шт
                  </a>
                </p>
              </div>
            </div>
            <div class="field">
              <label class="label">Цена</label>
              <div class="field has-addons">
                <p class="control">
                  <input class="input" type="number" placeholder="Стоимость">
                </p>
                <p class="control">
                  <a class="button is-static">
                    &#8381
                  </a>
                </p>
              </div>
            </div>

            <div class="control">
              <button class="button is-primary">Добавить</button>
            </div>
          </form>
        </div>

        <div class="column">
          <table class="table is-fullwidth">
            <thead>
            <tr>
              <th>№</th>
              <th>Наименование</th>
              <th>Количество</th>
              <th>Цена</th>
              <th></th>
            </tr>
            </thead>
            <tfoot>
            <tr>
              <th colspan="2">Итого</th>
              <th></th>
              <th></th>
              <th></th>
            </tr>
            </tfoot>
            <tbody>
            <tr v-for="(record, key) in records"
                :key="key">
              <th>{{ key + 1 }}</th>
              <td>{{ record.name }}</td>
              <td>{{ record.count }}</td>
              <td>{{ record.price }}</td>
              <td class="del">
                <button class="destroy" @click="removeRecord(record)"></button>
              </td>
            </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </section>
</template>

<script>

  export default {
    data() {
      return {
        records: [
          {
            name: 'hejf hE fe fwef',
            count: 10,
            price: 20,
          }, {
            name: 'hejf hE fe fwef',
            count: 10,
            price: 20,
          }, {
            name: 'hejf hE fe fwef',
            count: 10,
            price: 20,
          }, {
            name: 'hejf hE fe fwef',
            count: 10,
            price: 20,
          }, {
            name: 'hejf hE fe fwef',
            count: 10,
            price: 20,
          }, {
            name: 'hejf hE fe fwef',
            count: 10,
            price: 20,
          }, {
            name: 'hejf hE fe fwef',
            count: 10,
            price: 20,
          }, {
            name: 'hejf hE fe fwef',
            count: 10,
            price: 20,
          },
        ],
      };
    },
    methods: {
      removeRecord(rec) {
        this.records.splice(this.records.indexOf(rec), 1);
      },
    },
  };
</script>

<style lang="scss">
  @import '~bulma/bulma.sass';

  .table td.del {
    position: relative;
  }

  .table tr .destroy {
    outline: none;
    margin: auto 0 14px;
    padding: 0;
    position: absolute;
    right: 10px;
    bottom: 0;
    height: 30px;
    width: 30px;
    background: none;
    border: none;
    display: none;
    font-size: 30px;
    color: #cc9a9a;
    transition: color 0.2s ease-out;

    &:hover {
      color: #af5b5e;
    }
    &:after {
      content: '×';
    }
  }

  .table tr:hover .destroy {
    display: block;
  }
</style>
