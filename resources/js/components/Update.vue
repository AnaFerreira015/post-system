<template>
    <div class="container">
    <form>
        <div :class="['form-group m-1 p-3', successful ? 'alert-success' : '']">
        <span v-if="successful" class="label label-sucess">Updated!</span>
        </div>

        <div :class="['form-group m-1 p-3', error ? 'alert-danger' : '']">
        <span v-if="errors.title" class="label label-danger">
            {{ errors.title[0] }}
        </span>
        <span v-if="errors.body" class="label label-danger">
            {{ errors.body[0] }}
        </span>
        </div>

        <div class="form-group">
        <input type="title" ref="title" class="form-control" id="title" placeholder="Enter title" required>
        </div>

        <div class="form-group">
        <textarea class="form-control" ref="body" id="body" placeholder="Enter a body" rows="8" required></textarea>
        </div>

        <button type="submit" @click.prevent="update" class="btn btn-primary block">
        Submit
        </button>
    </form>
    </div>
</template>