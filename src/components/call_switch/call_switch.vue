<component class="component-call-switch">
    <!-- First loop through all the active calls -->
    <div :data-tooltip="callTitle(call)" class="call tooltip tooltip-left" :class="classes(call, 'call-button')"
        v-if="call.status !== 'new'" v-for="call in calls" @click="activateOrDeleteCall(call)">
        <icon :name="callIcon(call)"/>
    </div>
    <!-- New call always end up at the bottom -->
    <div :data-tooltip="callTitle(call)" class="call tooltip tooltip-left" :class="classes(call, 'call-button')"
        v-if="call.status === 'new'" v-for="call in calls" @click="activateOrDeleteCall(call)">
        <icon :name="callIcon(call)"/>
    </div>
    <!-- Create new Call button -->
    <div :data-tooltip="$t('setup new call')" class="call tooltip tooltip-left" v-if="newCallAllowed()" @click="createCall(false, false)">
        <icon name="dialpad"/>
    </div>
</component>
