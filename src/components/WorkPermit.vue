<template>
    <LayoutLong title="작업허가서">
        <!-- <Header /> -->
        <ProcessBar class="ProcessBar" />

        <ul class="list">
            <li class="list__labelText">
                <span>
                    {{ State }}
                </span>

                <span>
                    {{ Company }}
                </span>

                <span>
                    {{ Start }}
                </span>

                <span>
                    {{ End }}
                </span>
            </li>
            <li v-for="item in list" :data="item" class="list__textBox">
                <RedChip v-if="item.chip">
                    {{ item.RedChip }}
                </RedChip>

                <GreenChip v-else>
                    {{ item.GreenChip }}
                </GreenChip>
                <span class="list__textBox__company">
                    {{ item.label }}
                </span>

                <span class="list__textBox__start">
                    {{ item.count }}
                </span>

                <span class="list__textBox__end">
                    {{ item.end }}
                </span>
            </li>
        </ul>
    </LayoutLong>
</template>

<script>
import LayoutLong from "../Layout/LayoutLong.vue";
import Header from "./chip/Header.vue";
import ProcessBar from "../components/chip/ProcessBar.vue";
import Chip from "./chip/Chip.vue";
import RedChip from "./chip/RedChip.vue";
import GreenChip from "./chip/GreenChip.vue";

export default {
    components: { LayoutLong, Header, ProcessBar, Chip, RedChip, GreenChip },
    data() {
        return {
            State: "상태",
            Company: "소속",
            Start: "시작",
            End: "종료",

            list: [
                {
                    label: "지에스아이엘",
                    count: "13:02:10",
                    end: "15:02:10",
                    chip: true,
                },
                {
                    label: "서부",
                    count: "13:02:10",
                    end: "",
                    chip: false,
                },
                {
                    label: "지에스아이엘",
                    count: "13:02:10",
                    end: "15:02:10",
                    chip: true,
                },
                {
                    label: "지에스아이엘",
                    count: "13:02:10",
                    end: "",
                    chip: false,
                },
                {
                    label: "지에스아이엘",
                    count: "13:02:10",
                    end: "",
                    chip: false,
                },
                {
                    label: "지에스아이엘",
                    count: "13:02:10",
                    end: "",
                    chip: false,
                },
            ],
        };
    },
};
</script>

<style lang="scss" scoped>
@import "../scss/Color.scss";
@import "../scss/Font.scss";

.ProcessBar {
    margin-bottom: 14px;
}
.list {
    display: flex;
    flex-direction: column;

    padding: 0;
    gap: 16px;

    &__textBox {
        display: grid;
        align-items: center;
        grid-template-columns: 1fr 1fr 1fr 1fr;

        background: $Color-blue-002;
        border-radius: 6px;
        height: 55px;

        font-size: 15px;
        font-weight: $font-weight-500;

        &__company {
        }
    }

    &__labelText {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr;
    }

    &__start {
    }

    &__end {
    }
}
</style>
